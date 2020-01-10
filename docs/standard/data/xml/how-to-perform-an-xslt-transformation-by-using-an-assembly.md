---
title: 'Vorgehensweise: Ausführen einer XSLT-Transformation mittels einer Assembly'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76ee440b-d134-4f8f-8262-b917ad6dcbf6
ms.openlocfilehash: 9fd8656594730f29d28cbfdd130d322bfc000614
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710829"
---
# <a name="how-to-perform-an-xslt-transformation-by-using-an-assembly"></a>Vorgehensweise: Ausführen einer XSLT-Transformation mittels einer Assembly
Der XSLT-Compiler (xsltc.exe) kompiliert XSLT-Stylesheets und generiert eine Assembly. Die Assembly kann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden.  
  
### <a name="to-copy-the-xml-and-xslt-files-to-your-local-computer"></a>So kopieren Sie die XML- und die XSLT-Dateien auf den lokalen Computer  
  
- Kopieren Sie die XSLT-Datei auf den lokalen Computer, und nennen Sie sie &lt;legacyBold&gt;Transform.xsl&lt;/legacyBold&gt;.  
  
    ```xml  
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
      xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
      xmlns:user="urn:my-scripts">  
      <msxsl:script language="C#" implements-prefix="user">  
        <![CDATA[  
      public string discount(string price){  
        char[] trimChars = { '$' };  
        //trim leading $, convert price to type double  
        double discount_value = Convert.ToDouble(price.TrimStart(trimChars));  
        //apply 10% discount and round appropriately  
        discount_value = .9*discount_value;  
        //convert value to decimal and format as currency  
        string discount_price = discount_value.ToString("C");  
        return discount_price;  
      }  
      ]]>  
      </msxsl:script>  
      <xsl:template match="catalog">  
        <html>  
          <head></head>  
          <body>  
            <table border="1">  
              <tr>  
                <th align="left">Title</th>  
                <th align="left">Author</th>  
                <th align="left">Genre</th>  
                <th align="left">Publish Date</th>  
                <th align="left">Price</th>  
              </tr>  
              <xsl:for-each select="book">  
                <tr>  
                  <td>  
                    <xsl:value-of select="title"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="author"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="genre"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="publish_date"/>  
                  </td>  
                  <xsl:choose>  
                    <xsl:when test="genre = 'Fantasy'">  
                      <td>  
                        <xsl:value-of select="user:discount(price)"/>  
                      </td>  
                    </xsl:when>  
                    <xsl:otherwise>  
                      <td>  
                        <xsl:value-of select="price"/>  
                      </td>  
                    </xsl:otherwise>  
                  </xsl:choose>  
                </tr>  
              </xsl:for-each>  
            </table>  
          </body>  
        </html>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
- Kopieren Sie die XML-Datei auf den lokalen Computer, und nennen Sie sie `books.xml`.  
  
    ```xml  
    <?xml version="1.0"?>  
    <catalog>  
       <book id="bk101">  
          <author>Gambardella, Matthew</author>  
          <title>XML Developer's Guide</title>  
          <genre>Computer</genre>  
          <price>$44.95</price>  
          <publish_date>2000-10-01</publish_date>  
       </book>  
       <book id="bk102">  
          <author>Ralls, Kim</author>  
          <title>Midnight Rain</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-12-16</publish_date>  
       </book>  
       <book id="bk103">  
          <author>Corets, Eva</author>  
          <title>Maeve Ascendant</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-11-17</publish_date>  
       </book>  
       <book id="bk106">  
          <author>Randall, Cynthia</author>  
          <title>Lover Birds</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-09-02</publish_date>  
       </book>  
       <book id="bk107">  
          <author>Thurman, Paula</author>  
          <title>Splish Splash</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-11-02</publish_date>  
       </book>  
    </catalog>  
    ```  
  
### <a name="to-compile-the-style-sheet-with-the-script-enabled"></a>So kompilieren Sie das Stylesheet mit aktiviertem Skript  
  
1. Bei Ausführung des folgenden Befehls von der Eingabeaufforderung werden die beiden Assemblys `Transform.dll` und `Transform_Script1.dll` erstellt. (Dies ist das Standardverhalten. Sofern nicht anders angegeben, erhalten die Klasse und die Assembly standardmäßig denselben Namen wie das Hauptstylesheet.):  
  
    ```console  
    xsltc /settings:script+ Transform.xsl  
    ```
  
    Der folgende Befehl legt den Klassennamen explizit auf &lt;legacyBold&gt;Transform&lt;/legacyBold&gt; fest:  
  
    ```console  
    xsltc /settings:script+ /class:Transform Transform.xsl  
    ```  
  
### <a name="to-include-the-compiled-assembly-as-a-reference-when-you-compile-your-code"></a>So binden Sie die kompilierte Assembly beim Kompilieren Ihres Codes als Verweis ein  
  
1. Sie können in Visual Studio eine Assembly einbinden, indem Sie im Projektmappen-Explorer oder von der Eingabeaufforderung aus einen Verweis hinzufügen.  
  
2. Wenn Sie mit der Eingabeaufforderung und C# arbeiten, verwenden Sie folgenden Befehl:  
  
    ```console  
    csc myCode.cs /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
3. Wenn Sie mit der Eingabeaufforderung und Visual Basic arbeiten, verwenden Sie folgenden Befehl:  
  
    ```console  
    vbc myCode.vb /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
### <a name="to-use-the-compiled-assembly-in-your-code"></a>So verwenden Sie die kompilierte Assembly in Ihrem Code  
  
Im folgenden Beispiel wird gezeigt, wie Sie die XSLT-Transformation mithilfe des kompilierten Stylesheets ausführen können.  
  
[!code-csharp[XslTransform_XSLTC#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslTransform_XSLTC/CS/XslTransform_XSLTC.cs#1)]
[!code-vb[XslTransform_XSLTC#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslTransform_XSLTC/VB/XslTransform_XSLTC.vb#1)]  
  
Wenn Sie eine dynamische Verknüpfung zur kompilierten Assembly herstellen möchten, ersetzen Sie im Beispiel oben
  
```csharp  
xslt.Load(typeof(Transform));  
```  
  
mit  
  
```csharp 
xslt.Load(System.Reflection.Assembly.Load("Transform").GetType("Transform"));  
``` 
  
im oben aufgeführten Beispiel. Weitere Informationen zur Assembly. Load-Methode finden Sie unter <xref:System.Reflection.Assembly.Load%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [XSLT-Compiler („xsltc.exe“)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
- [XSLT Transformations (XSLT-Transformationen)](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
