# The sample project of FitNesse

Use Cucumber and Java to implement the Hotel World Clocks kata and refactor it to Observer design pattern. In this kata, a hotel has 5 clocks showing the time of Beijing (UTC+8), London (UTC+0), Moscow (UTC+4), Sydney (UTC+10), and New York (UTC-5). You have to consider daylight saving time (DST) for cities like London and New York in this kata. When the time of each one of these clocks is set due to incorrect time or start/end of daylight saving period, the time of all other clocks will be set automatically. The hotel would add more clocks for different cities in the future.

# Steps
1. Write a test spreadsheet `hotel_world_clocks_test_tables.xlsx`
2. Start FitNesse server by `java -jar fitnesse-standalone.jar -p 8080`
3. Visit the homepage of FitNesse by http://localost:8080
4. Edit the homepage and add the test wiki page `KataHotelWorldClocks`
5. Replace the contents of the wiki page with the following
```
   !define TEST_SYSTEM {slim}
   !path fitnesse-standalone.jar
   !path C:\my-fixture-code.jar

   !|import                      |
   |my.name.space|
```
6. Append the contents from the test spreadsheet to the test wiki page
7. Make the test wiki page testable by clicking "Tools > Properties > Test > Save"
8. Click "Test" on the test wiki page
9. Got an error message: `Could not invoke constructor for AHotelLobbyHasFiveClocks[0]`
10. Add a class `AHotelLobbyHasFiveClocks` under the namespace `com.wubinben.katas.bdd.fitnesse` in `src/main/java` to fix the error above
11. Run command `mvn clean package`
12. Edit the test wiki page to make FitNesse to access the Java classes
```
!path /Users/twer/OOR/katas/remote/hotel-world-clocks-fitnesse/target/hotel-world-clocks-fitnesse-1.0-SNAPSHOT.jar                com.wubinben.kata.hwc
!|import                      |
|com.wubinben.katas.bdd.fitnesse|
```
13. Press "Test" on the test wiki page. The error above should be fixed
14. Fix all errors

