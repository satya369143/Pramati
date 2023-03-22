# CSS Selector Selenium WebDriver 

Open **Chrome** and navigate to application homepage.

Open **inspect element** and select **Search box** in the page to inspect it.

1. ### Tag and ID :

   * **Syntax** :   css=tag#id
   * **Example** : css=input#searchq

2. ### **Tag and Class:**

   * **Syntax** : css=tag.class

   * If class name contains spaces then for each spaces put dot<.> 

     ​		- pramati technologies private limited  

   * **Syntax** : css=tag.pramati.technologies.private.limited

   * **Example** : css=input.ui-autocomplete-input

3. ### **Tag and Attribute** :

   * **Syntax** : css=tag[attribute=value]
   * **Example** : css=input[name=searchq]

4. ### **Tag, Class And Attribute** :

   * **Syntax** : css=tag.class[attribute=value]
   * **Example** : css=input.ui-autocomplete-input[name=searchq]

5. ### **SUB-STRING MATCHES** :

   * **Starts With (^)**
     * **Syntax** : css=tag<[attribute^=prefix of the string]>
     * **Example** : css=input[name^='se']
   * **Ends With ($)**
     * **Syntax** : css=tag<[attribute$=suffix of the string]>
     * **Example** : css=input[name$='hq']
   * **Contains (*)**
     * **Syntax** : css=tag<[attribute*=sub string]>
     * **Example** : css=input[name*='se']

6. ### **Locating Child Elements(Direct Child)** :

   * **Syntax** : parentLocator>childLocator
   * **CSS Locator** : div#buttonDiv>button
   * **Explanation** : ‘div#buttonDiv button’ will first go to div element with id ‘buttonDiv’ and then select ‘button’ element inside it (which may be its child or sub child).

7. ### **Locating elements inside other elements (child or sub-child)** :

   *  **Syntax** : parentLocator>locator1 locator2
   * **CSS Locator** : div#buttonDiv button
   * **Explanation** : ‘div#buttonDiv button’ will first go to div element with id ‘buttonDiv’ and then select ‘button’ element inside it (which may be its child or sub child).

8. ### **Locating nth Child** :

   * **Example** : css= .global_search_select_holder ul.inline-list li:nth-of-type(4) 
   * To select the last child element
     * **Example** : css= .global_search_select_holder ul.inline-list li:last-child 
