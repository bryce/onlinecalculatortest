# Online Calculator Test Plan 
# for
      /$$$$$$                               /$$  /$$$$$$          
     /$$__  $$                             |__/ /$$__  $$         
    | $$  \__/  /$$$$$$  /$$$$$$  /$$$$$$$  /$$| $$  \__//$$   /$$
    | $$ /$$$$ /$$__  $$|____  $$| $$__  $$| $$| $$$$   | $$  | $$
    | $$|_  $$| $$  \__/ /$$$$$$$| $$  \ $$| $$| $$_/   | $$  | $$
    | $$  \ $$| $$      /$$__  $$| $$  | $$| $$| $$     | $$  | $$
    |  $$$$$$/| $$     |  $$$$$$$| $$  | $$| $$| $$     |  $$$$$$$
    \______/ |__/      \_______/|__/  |__/|__/|__/      \____  $$
                                                         /$$  | $$
                                                        |  $$$$$$/
                                                         \______/ 

### By Bryce Clarke
### September 17, 2017

## Table of Contents
 ### [Requirements](#requirements)
#### [Explicit Requirements](#explicit-requirements)
#### [Implicit Requirements](#implicit-requirements)

### Types of Testing 
#### [Functional](#functional)
#### [Browser / Device Coverage](#Browser-Device)
#### [Performance](#Performance)
#### [Security](#Security)
#### [Accessibility](#Accessibility)

### Test Cases
#### [Functional Cases](#functional-cases)
#### [Performance Cases](#performance-cases)
#### [Accessibility Cases](#accessibility-cases)
#### [Cross Browser / Device Cases](#browser-device-cases)

### [Test Execution](#test-execution)

### [Issue Tracking](#issue-tracking)

### [Success Criteria](#success-criteria)



### Requirements <a id="requirements"></a>

### Explicit Requirements <a id="#explicit-requirements"></a>

The following requirements are listed on the online calculator pages

https://www.theonlinecalculator.com/

https://www.calculatorsoup.com/calculators/math/basic.php

These are the core business requirements that the application must meet. 


| Requirement id |Requirement    | Area |
| ------------- |:-------------:| -----:|
| R1 | Calculator has decimal precision up to 10 digits regardless of decimals | Operations| |
| R2 | mc key will clear calculator memory | Keys |
| R3 | m+ key add displayed value to memory | Keys |
| R4 | m- key will subtract displayed value from memory | Keys |
| R5 | mr key will display the memory value | Keys |
| R6 | CE key will Clear Entry: clear current display value, changes to CE TO AC key | Keys |
| R7 | AC key will clear all and start a new operation | Keys |
| R8 | √x key will take the square root of the displayed value and display it | Keys |
| R9 | +/- key will change the sign of the displayed value from positive to negative or vice versa | Keys |
| R10 | π key will display the value of π as 3.141592654 to use in a calculation | Keys |
| R11 | x² key will square the displayed value and display it | Keys |
| R12 | R2 key will Round to 2 decimals: round the current display value to 2 decimal places such as in money or currency format | Keys |
| R13 | R0 key will Round to 0 decimals: round off the current display value to 0 decimal places | Keys |
| R14 | % key will Percent: use displayed value to calculate a percentage | Keys |
| R15 | The calculator memory is at 0 until you hit m+ or m- | Keys |
| R16 | Each time you hit m+ the number on the display is added to the number in the calculator memory  | Keys | 
| R17 | Each time you hit m- the number on the display is subtracted from the number in the calculator memory  | Keys |
| R18 | To recall the number in the calculator memory hit mr  | Keys | 
| R19 | To zero out the memory hit mc  | Keys |
| R20 | Use AC to clear out the current calculation  | Keys | 
| R21 | Use CE to clear out the most recent entry. Note that if the AC key is not visible, hit CE and then AC to clear out your calculation | Keys |
| R22 | Multiplication and Division will convert the displayed value to a percent in decimal form and complete the operation when you press [=] | Percentages| 
| R23 | Addition and Subtraction will add or subtract the percentage of a value | Percentages|
| R24 | Handle Tax Calculation and adding tax | Tax |
| R25 | Zoom: Increase the size of the calculator in your browser using your browser's zoom feature. The size of the calculator, text and buttons changes proportionately | Accessibility |
| R26 | Touch Screen Zoom: Increase the size of the calculator on your touch screen by zooming with your fingers. The size of the calculator, text and buttons changes proportionately | Accessibility |
| R27 | Text Size: In some browsers, such as Chrome desktop, you can change the text size in your browser settings and the size of the calculator, text and buttons will get larger or smaller proportionately  | Accessibility |
| R28 | Keyboard Control: You can use the calculator without a mouse by tabbing among the calculator keys. Press "Enter" when a key is focused. This method can be arduous however, since you must tab through all keys in sequence | Accessibility |
| R29 | Number Keypad Control: You can use the calculator with certain keypads and browsers for integers, clear, and the basic functions of addition, subtraction, multiplication, and division. It works on a MacBook Pro number keypad in Chrome and Opera but not Safari or FireFox | Accessibility |

### Implicit Requirements / Assumptions

The following are requirements that not specific listed in any of the application pages. 

Normally these requirements would be discussed with the product and development team in order to understand the business case for each. For this assignment we will have to make some assumptions about the functionality/scope in leiu of having those discussions. 

#### Scope of Testing
#### Out of scope for this exercise 

The version of the same calculator on calculatorsoup.com or the widget version of the calculator

See following links 

https://www.calculatorsoup.com/calculators/math/basic.php

https://www.calculatorsoup.com/calculators/calculator-widgets.php?folder=math/&folderName=Math&folder2=&folderName2=&calc=1&pop=1&url=https://www.calculatorsoup.com/calculators/math/basic.php&h1=Basic%20Calculator&pop_w=400&pop_h=600

Calculator only allows one operation at a time so we will not test that it follows correct order of operations (i.e. BODMAS)

#### Functionality

Requirements for standard best practises for the core functionality of the app. 

| Requirement id |Requirement    | Area |
| ------------- |:-------------:| -----:|
| AR01 |Backspace / delete should remove last digital in display | Operations||
| AR02 |User should be able to type in numbers and operations via keyboard | Operations| |
| AR03 |The display should correctly display up to twenty digits including twenty digit real number and negative numbers| Display |
|AR04 | If a equation returns a value greater than 20 digital number then the answer should display in exponent format | Display|
    
#### Rounding
There is no specific rule in the requirements about rounding so we will assume the calculator follows the same rules as other rounding calculators on the same site. 

Example: 

https://www.calculatorsoup.com/calculators/math/roundingnumbers.php

The calculator will follow these rules:

| Requirement id |Requirement    | Area |
| ------------- |:-------------:| -----:|
| AR05 |If the digit in the next smallest place value is less than five (0, 1, 2, 3, or 4), you leave the digit you want to round to as-is. Any digits after that number become zeros, or drop-off if they're located after the decimal point. | Rounding| 
| AR06 |If the next smallest place value is greater than or equal to five (5, 6, 7, 8, or 9), you increase the value of the digit you're rounding to by one (+1) | Rounding|
        
We will not assume the calculator uses Banker's Rounding rules (round to nearest even number) for this excerise


### Browser / Device support
Since we don't have stats from google analytics or other web/device analytics sources or direction from product team for supported browsers/devics. We are going to use the following sources to determine which browsers / devices we will test the platform with.    
Desktop Browsers stats
http://gs.statcounter.com/browser-version-market-share/desktop/canada/#monthly-201703-201708-bar

Device Screen Resolution
http://gs.statcounter.com/screen-resolution-stats/mobile-tablet/canada/#monthly-201703-201708-bar

Desktop OSes
http://gs.statcounter.com/os-market-share/desktop/canada#monthly-201703-201708-bar

iOS versions
http://gs.statcounter.com/os-version-market-share/ios/mobile-tablet/canada#monthly-201703-201708-bar

Android versions
http://gs.statcounter.com/os-version-market-share/android/mobile-tablet/canada#monthly-201703-201708-bar

Combined stats for OSes
http://gs.statcounter.com/os-market-share/desktop-mobile-tablet/canada/#monthly-201703-201708-bar


We will be testing any browser / device will a total page view popularity of > 5% of total views in the last 6 months in Canada. This ensures the site works with the majority of our users and limits the scope of support browsers/devices. 

With this criteria the following Browser/device/OSes combinations are in scope. 

| Browser |Device | OS | % of Page views| Platform id| 
| ------------- |-------------| -----| -----:| -----:|
| Safari | IPhone 7 | iOS 10.3| 53| 1|
| Safari | IPhone 6 | iOS 9.3| 53| 2|
| Safari | Ipad 12 in| iOS 10.3| 53| 3|
| Safari | Ipad 12| iOS 10.3| 53| 4|
| Safari | Ipad Pro | iOS 10.3| 53| 5|
| Chrome | Galaxy S7 | 6.0 | 53| 6|
| Chrome | Galaxy S8 | 7.0 | 53| 7|
| Safari 10.1 | Mac | OSX | 53| 8|
| Chrome 60 | Windows | 10 | 53| 9|
| Chrome 59 | Windows | 10 | 53| 10|
| IE 11 | Windows | 10 | 53| 11|
| FF 54 | Windows | 10 | 53| 12|

If we had knowledge of browser/devices clients needed to support or known new products coming on the market (ie iphone X) we would add those to supported group as well.

### Accessibility

There are no specific overall requirements for accessibility of the site so we will follow WCAG 2.0A standards. This will ensure the site has basic accessiblility for  a wide range of people with disabilities

WCAG 2.0A criteria is listed below:        
https://www.w3.org/WAI/WCAG20/quickref/?currentsidebar=%23col_overview&levels=aa%2Caaa&technologies=pdf%2Cflash%2Csl#top

We will use to following requirements to met that criteria along with the existing requirements on the page. 

| Requirement id |Requirement    | Area |
| ------------- |:-------------:| -----:|
| AR07 |Keyboard navigation follows logical order| Accessibility|
| AR08 |All elements on page have alt or aria tags| Accessibility|
| AR09 |Confirm WCAG Level 2A using aXe| Accessibility|
    
    
### Performance

There are no specific performance goals listed for the site and the site itself is client-side only. We will not do traditional load and stress testing. Instead we will focus on client side rendering on load. 

We will use tools such as webpagetest and lighthouse to measure client side load time to ensure it meets acceptable load times. 

We will assume the following measures

| Requirement id |Requirement    | Area |
| ------------- |:-------------:| -----:|
| AR10 |On Desktop the page loads under 2 seconds on normal connection| Accessibility|
| AR11 |On Mobile the page loads under 3 seconds on 3g connection| Accessibility|
| AR12 |Lighthouse page loads measure under 2 seconds| Accessibility|

These 

### Security
There are no specific security requirements for the site and it does not store any PII (ie no database or cookies) so we will not perform any specific security tests on the site. 

### Analytics


## Test Cases

### Functional Cases <a id="functional-cases"></a>
        
Operations| Functionality        

|Test Case id|Test Case Description|Steps|Expected Results|Associated Requirement|Area||
|-------------|:-------------:|-----|-----|-----|-----|-----|-----
|TC01|Addition of two positive integers|5 + 12|17|N/A|Operations||
|TC02|Addition of two negative integers|-4 + -444|-448|N/A|Operations||
|TC03|Addition of one positive and one negative integer where positive is greater|12 + -7|5|R1|Operations||
|TC04|Multiplication of two negative integers|-3 * -33|99|N/A|Operations||
|TC05|Multiplication of one negative and one positive integer|-4 * 4|16|N/A|Operations||
|TC06|Division of two positive integers|81 / 3|27|N/A|Operations||
|TC07|Division of two negative integers|-25 / -5|5|N/A|Operations||
|TC08|Division of one positive integer and one negative integer|-9 / 3|-3|N/A|Operations||
|TC09|Division of a positive integer by zero|9 /0|Not a Number message displayed|N/A|Operations||
|TC10|Division of a negative integer by zero|-11 / 0|Not a Number message displayed|N/A|Operations||
|TC11|Clear entry key works correctly|5 + 5 + 5 + -> Press CE|AC key changes to CE and 15 removed from display|R6|Operations||
|TC12|AC key works correctly|8 + 8 = -> type 8 -> Press CE -> press + -> press 3|19 is displayed|R7|Operations||
|TC13|Square root of a positive integer|125 -> √x|11.18|R8|Operations||
|TC14|Square root of a square root able integer|144 -> √x|12|R8|Operations||
|TC15|Square root of a negative integer|-144 -> √x|Not a Number message displayed|R8|Operations||
|TC16|Square root of a positive integer where decimals > 10|14.123456789012 -> √x|3.76|R8|Operations||
|TC17|Square of a positive integer|3 -> x²|9|R11|Operations||
|TC18|Square of a negative integer|-9 -> x²|81|R11|Operations||
|TC19|Square of a real with 6 decimals places|10.12345 -> x²|10.4843613839 (under 10 places displayed)|R11|Operations||
|TC20|Type a positive integer and press +/-|23 -> press +/=|-23|R9|Operations||
|TC21|Type a negative integer and press +/-|Result|R9|R9|Operations||
|TC22|Disallow letters as input|Type granify rules|Nothing displayed|N/A|Operations||
|TC23|Disallow non-alphanumeric characters|Type #@%%`~?'|Nothing displayed|N/A|Operations||
|TC24|MR button start at zero|press mc -> hit MR button|Nothing displayed|R15|Operations||
|TC25|Check link at bottom of calculator|Click on CalculatorSoup text and ensure it goes to https://www.calculatorsoup.com/calculators/math/basic.php|N/A|N/A|Misc||
|TC26|Check contact me links at bottom of the page|Click on both contact me links at bottom of the page|Ensure you are redirected to contact page (https://www.calculatorsoup.com/contact.php)|N/A|Misc||
|TC27|Check legal links at bottom of the page|Click on legal information|Ensure you are redirected to contact page (https://www.theonlinecalculator.com/legal.htm)|N/A|Misc||
|TC28|Check the other calculator links on the bottom of the page|Click on all the links under other calculator links|Ensure you are redirected to the following: Calculators Online at CalculatorSoup (https://www.calculatorsoup.com),Time Card Calculator (http://www.timecardcalculator.net),Mobile Time Card Calculator (http://m.timecardcalculator.net)|N/A|Misc||
|TC29|Check CalculatorSoup link at bottom of the page|Click on CalculatorSoup link in the footer|Ensure you are redirected to contact page (CalculatorSoup.com)|N/A|Misc||
|TC30|Adding value to memory and recalling it|press mc -> type 9 -> press m+ button -> type 1 -> press mr button|9 appears on screen|R5|Operations||
|TC31|Check 10 digit decimal precision|1.55555555555 + 2.44444444444|~3.9999999999 is displayed|R1|Operations||
|TC32|Clearing memory|press mc -> type 9 -> press m+ button -> press mc -> hit mr button|Zero is displayed|R2,R19|Memory||
|TC33|Confirm memory is stored after cleaning operation|press mc -> type 9 -> press m+ button -> press ce -> press ac -> press mr button|9 should be displayed|R5,R20|Memory||
|TC34|Pie can be stored as memory object|press mc -> press pie -> press m+ button -> press mr button|3.1415926536 should be displayed|R10|Memory||
|TC35|Doesn''t truncate integers when put in memory|press mc -> type 1234567890123456790 -> press m+ -> press ce -> press mr|1234567890123456790 is displayed|R1|Memory||
|TC36|Correct truncates memory object to 10 real with decimals|press mc -> type 100.12345679012 -> press m+ -> press ce -> press mr|100.1234567890 is displayed|R1|Memory||
|TC37|Memory does not last more than a browser session|press mc -> type 999 -> press m+ -> type 10 -> press mr -> close browser -> press mr again|Memory should be clear |N/A|Memory||
|TC38|Adding new value to existing memory|press mc -> type 9 -> press m+ -> press ce -> press mr -> type 10.12 -> press m+ -> press mr|19.12 is displayed|R16,R21|Memory||
|TC39|Removing new value from from memory|press mc -> type 9 -> press m- -> press ce -> press mr -> type 1.5 -> press m- -> press mr|8.5 is displayed|R4,R17|Memory||
|TC40|Using memory in equation|press mc -> type 9 -> press m+ -> press CE -> type 5 -> press  * -> press mr|27 is displayed|R3,R18|Memory||
|TC41|Display should correctly display up to twenty digits|Type 12345678901234567890|12345678901234567890 should be displayed and not cutoff|AR03|Display||
|TC42|Display should correctly display up to twenty digits|Type 12.123456789012345678|12.1234567890123 Should be displaued|AR03|Display||
|TC43|If a equation returns a value greater than 20 digital number then the answer should display in exponent format|9999999999 squared|9.999999999998e+25 is displayed|AR04|Display||
|TC44|Rounding two decimals places on an integer|type 5 -> press R2|5 is displayed|R12|Rounding||
|TC45|Rounding two decimals place on a single decimal number|type 5.5 -> press R2|5.5 is displayed|R12|Rounding||
|TC46|Rounding up on  two decimals place on a two decimal number|type 5.55 -> press R2|5.56 is displayed|AR06|Rounding||
|TC47|Rounding down on two decimals place on a five decimal number|type 5.444444 -> press R2|5.44 is displayed|AR05|Rounding||
|TC48|Rounding up on two decimals place on a negative 10 decimal number|type -5.1111111119 -> press R2|-5.12 is displayed|AR06|Rounding||
|TC49|Rounding to two decimals when  last digital equal to 5|type 5.5555 -> press R2|5.56 is displayed|AR06|Rounding||
|TC50|Rounding to zero on integer and press R0|type 5 -> R0|5 is displayed|R13|Rounding||
|TC51|Rounding to zero - single place|type 5.4 -> press R0|5 is displayed|R13|Rounding||
|TC52|Rounding up to zero on single place|type 5.6 -> press R0|6 is displayed|AR06|Rounding||
|TC53|Rounding down  to zero on multiple places|type 5.4444 -> press R0|5 is displayed|AR05|Rounding||
|TC54|Rounding up to zero on multiple places|type 5.5556 -> press R0|6  is displayed|AR06|Rounding||
|TC55|Rounding up to zero on negative value|type 5.6-> press +/- -> press R0|-6  is displayed|AR06|Rounding||
|TC56|Rounding to zero when last digital equal to 5|type 5.55555 -> press R0|6 is displayed|AR06|Rounding||
|TC57|Turning integer into percentage|type 50 -> press %|.50 is displayed|R14|Percentage||
|TC58|Turning real with decimal into percentage|type 2.25 -> press %|0.0225 is displayed|R14|Percentage||
|TC59|Turning a decimal into percentage|type 0.50 -> press %|0.005 is displayed|R14|Percentage||
|TC60|Calculating percentage of a number (percentage first)|type 20 -> press % -> press * -> type 25|5 is displayed|R22|Percentage||
|TC61|Calculating percentage of a number (percentage last)|type 25 -> press * -> type 20 -> press % -> press =|5 is displayed|R22|Percentage||
|TC62|Calculating and adding tax to an item (percentage first)|Type 13.5 -> press % -> press * -> type 125.55 ->  press + -> type 125.55 -> press = -> press R2 |142.50 is displayed|R23,R24|Tax||
|TC63|Calculating and adding tax to an item (percentage last)|Type 125.55 -> press + > type 13.5 -> press % -> press = -> Press R2|142.50 is displayed|R23,R24|Tax||
|TC64|Multiple operations Use Case - squares and division|Type 9 -> press square root -> press + -> type 6 -> press squared button -> press / -> press 3 -> press =|27 is displayed|N/A|Use Cases||
|TC65|Multiple operations Use Case - rounding and multiplication|Type 9.3343 -> press * -> type 124.2221 -> press R0 -> press + -> 33|159.53 is displayed|N/A|Use Cases||
|TC66|Press tab to navigate through calculator keys|Load app ->Press tab multiple times|The input focus should move between the calculator key as you press tab|R28|Accessibility||
|TC67|Action calculator key using enter key|Load app -> press tab and select a key -> press enter|Key select should be actioned|R28|Accessibility||
|TC68|Keyboard navigate follows a logical order for calculator actions|Load app -> press tab multiple times|As you press tab the input focus you start on the display and cycle through numbers then operators first|AR07|Accessibility||
|TC69|Enter equation into calculator using keyboard only (not keypad)|Load app -> type 1 + 3 = on keyboard|4 should be displayed|AR02|Accessibility||
|TC70|Enter equation into calculator using keypad only|Load app -> turn on keypad (if required) -> and type 422 + 222 =|644 should be displayed|R29|Accessibility||
|TC71|Press delete / backspace key to delete last character displayed|Enter 999 on calculator and press delete/backspace |99 should be displayed|AR01|Accessibility||
|TC72|Using browser zooming correctly re sizes calculator  |Zoom page on browser by 200%|Calculator should re size to zoomed screen|R25|Accessibility||
|TC73|Using touch zooming correctly re sizes calculator|Pinch and zoom on screen to zoom into app|Calculator should re size to zoomed screen|R26|Accessibility||
|TC74|Increase text size to ensure app functions with new text size|Go into browser/device settings and change text size to 2x greater|Calculator continues to function and display properly|R27|Accessibility||
|TC75|All elements on page have alt or aira tags|Chrome -> dev tools -> inspect all elements in calculator for tags|All elements have correct tags|N/A|Accessibility||
|TC76|Confirm WCAG Level 2A validate is met|Chrome -> dev tools -> run aXe chrome extension on site |No errors are found|N/A|Accessibility||
|TC77|Check page load time (webpagetest browser)|goto webpagetest.org and put in theonlinecalculator.com and select Dallas Thinkpad T4430 with chrome and run|Page is fully loaded under 2 seconds|AR10|Performance||
|TC78|Check page load time (webpagetest mobile)|goto webpagetest.org and put in theonlinecalculator.com and select S7 with chrome and connection = mobile 3g fast and run|Page is fully loaded under 3 seconds|AR11|Performance||
|TC79|Check page load time (Lighthouse)|Desktop chrome -> dev tools -> audits tab -> peform audit -> select performance |Page is fully loaded under 2 seconds|AR12|Performance||

### Test Execution <a id="test-execution"></a>

The test execution will be tracked on the following google sheet



### Issue Tracking <a id="issue-tracking)"></a>
All issues will be reported on the repo's issue tracker on github

https://github.com/bryce/onlinecalculatortest/issues

All the issues found during testing will be logged using the following scale

S1 = Critical (The defect affects critical functionality or critical data. It does not have a workaround.)

S2 = Major (The defect affects major functionality or major data. It has a workaround but is not obvious and is difficult)

S3 = Minor (The defect affects minor functionality or non-critical data. It has an easy workaround)

S4 = Trivial (It does not impact productivity or efficiency)

The issues will be review with product and dev to ensure agreement of severity and its priority

### Success Criteria <a id="success-criteria)"></a>

Once a complete test cycle has been done, all the issues will be reviewed with bth the product and development leads to determine what issues are required to be fixed before release to production. Once those issues are determined the testers will test those issues as they are released and once all those issues have been fixed, a final full regression cycle will be run. 

This process of test, review and test will continue until there are no more launch critical issues and QA will test off on the release. 

