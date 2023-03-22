# XPath

![](https://www.guru99.com/images/3-2016/032816_0758_XPathinSele1.png)

1. **Basic Xpath**:
   * Xpath=//input [@type=’password’]
   * Xpath=//label [@id=’label1′]
   * Xpath=//*[@class=’test-tuts’]
   * Xpath=//a [@href=’http: //softwaretestingclass.com/’]
2. **Contains()**:
   * Xpath=//*[contains (@type, ‘sub-type’)]
   * Xpath=//* [contains (@name, ‘button’)]
   * Xpath=//*[contains(text (),’testing’)]
   * Xpath=//*[contains (@href,’softwaretestingclass.com’)]
   * Xpath=//h4/a[contains(text(),'SAP M')]
3. **Using OR & AND**:
   * Xpath=//*[@type=’submit’ OR @name=’buttonSubmit’]
   * Xpath=//input[@type=’submit’ AND @name=’buttonEnter’]
4. **Start-with function**:
   * Xpath=//label[starts-with(@id, ‘message’)]
   * Xpath=//a[starts-with(@id,’link-si’)]
   * Xpath=//a[starts-with(@id,’link-sign’)]
5. **Parent**:
   * Xpath=//*[@id=’soft-test-class’]//parent::div
   * Xpath=//*[@id=’soft-test-class’]//parent::div[1]
6. **Child**:
   * Xpath=//*[@id=’navigation-list’]/child::li
   * Xpath=//*[@id=’navigation-list’]/child::li[2]
7. **Self**:
   * Xpath =//*[@type=’text’]//self::input
8. **Sibling**:
   1. **Following**:
      * Xpath=//*[@type=’password’]//following::input
      * Xpath=//*[@type=’password’]//following::input[2]
   2. **Following-sibling**:
      * Xpath=//div[@class='canvas- graph']//[a[@href='/accounting.html'][i[@class='icon-usd']][i[@class='icon-usd']]/following-sibling::h4
      * xpath=//*[@type=’text’]//following-sibling::input
   3. **Preceding**:
      * Xpath=//*[@type=’text’]//preceding::input
      * Xpath=//*[@type=’text’]//preceding::input[3]
   4. **Ancestor**:
      * Xpath=//*//ancestor::p
      * Xpath=//*//ancestor::div [2]
   5. **Descendant**:
      * Xpath=//*[@id=’soft-test-class’]//descendant::a
      * Xpath=//*[@id=’soft-test-class’]//descendant::a[1]