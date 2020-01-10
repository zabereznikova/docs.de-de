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
# <a name="how-to-perform-an-xslt-transformation-by-using-an-assembly"></a><span data-ttu-id="ceb0b-102">Vorgehensweise: Ausführen einer XSLT-Transformation mittels einer Assembly</span><span class="sxs-lookup"><span data-stu-id="ceb0b-102">How to: Perform an XSLT Transformation by Using an Assembly</span></span>
<span data-ttu-id="ceb0b-103">Der XSLT-Compiler (xsltc.exe) kompiliert XSLT-Stylesheets und generiert eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="ceb0b-104">Die Assembly kann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-104">The assembly can be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-copy-the-xml-and-xslt-files-to-your-local-computer"></a><span data-ttu-id="ceb0b-105">So kopieren Sie die XML- und die XSLT-Dateien auf den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="ceb0b-105">To copy the XML and XSLT files to your local computer</span></span>  
  
- <span data-ttu-id="ceb0b-106">Kopieren Sie die XSLT-Datei auf den lokalen Computer, und nennen Sie sie &lt;legacyBold&gt;Transform.xsl&lt;/legacyBold&gt;.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-106">Copy the XSLT file to your local computer and name it Transform.xsl.</span></span>  
  
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
  
- <span data-ttu-id="ceb0b-107">Kopieren Sie die XML-Datei auf den lokalen Computer, und nennen Sie sie `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-107">Copy the XML file to your local computer and name it `books.xml`.</span></span>  
  
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
  
### <a name="to-compile-the-style-sheet-with-the-script-enabled"></a><span data-ttu-id="ceb0b-108">So kompilieren Sie das Stylesheet mit aktiviertem Skript</span><span class="sxs-lookup"><span data-stu-id="ceb0b-108">To compile the style sheet with the script enabled.</span></span>  
  
1. <span data-ttu-id="ceb0b-109">Bei Ausführung des folgenden Befehls von der Eingabeaufforderung werden die beiden Assemblys `Transform.dll` und `Transform_Script1.dll` erstellt. (Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-109">Executing the following command from the command line creates two assemblies named `Transform.dll` and `Transform_Script1.dll` (This is the default behavior.</span></span> <span data-ttu-id="ceb0b-110">Sofern nicht anders angegeben, erhalten die Klasse und die Assembly standardmäßig denselben Namen wie das Hauptstylesheet.):</span><span class="sxs-lookup"><span data-stu-id="ceb0b-110">Unless otherwise specified, the name of the class and the assembly defaults to the name of the main style sheet):</span></span>  
  
    ```console  
    xsltc /settings:script+ Transform.xsl  
    ```
  
    <span data-ttu-id="ceb0b-111">Der folgende Befehl legt den Klassennamen explizit auf &lt;legacyBold&gt;Transform&lt;/legacyBold&gt; fest:</span><span class="sxs-lookup"><span data-stu-id="ceb0b-111">The following command explicitly sets the class name to Transform:</span></span>  
  
    ```console  
    xsltc /settings:script+ /class:Transform Transform.xsl  
    ```  
  
### <a name="to-include-the-compiled-assembly-as-a-reference-when-you-compile-your-code"></a><span data-ttu-id="ceb0b-112">So binden Sie die kompilierte Assembly beim Kompilieren Ihres Codes als Verweis ein</span><span class="sxs-lookup"><span data-stu-id="ceb0b-112">To include the compiled assembly as a reference when you compile your code.</span></span>  
  
1. <span data-ttu-id="ceb0b-113">Sie können in Visual Studio eine Assembly einbinden, indem Sie im Projektmappen-Explorer oder von der Eingabeaufforderung aus einen Verweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-113">You can include an assembly in Visual Studio by adding a reference in the Solution Explorer, or from the command line.</span></span>  
  
2. <span data-ttu-id="ceb0b-114">Wenn Sie mit der Eingabeaufforderung und C# arbeiten, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ceb0b-114">For the command line with C#, use the following:</span></span>  
  
    ```console  
    csc myCode.cs /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
3. <span data-ttu-id="ceb0b-115">Wenn Sie mit der Eingabeaufforderung und Visual Basic arbeiten, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ceb0b-115">For the command line with Visual Basic, use the following</span></span>  
  
    ```console  
    vbc myCode.vb /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
### <a name="to-use-the-compiled-assembly-in-your-code"></a><span data-ttu-id="ceb0b-116">So verwenden Sie die kompilierte Assembly in Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="ceb0b-116">To use the compiled assembly in your code.</span></span>  
  
<span data-ttu-id="ceb0b-117">Im folgenden Beispiel wird gezeigt, wie Sie die XSLT-Transformation mithilfe des kompilierten Stylesheets ausführen können.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-117">The following example shows how to execute the XSLT transformation by using the compiled style sheet.</span></span>  
  
[!code-csharp[XslTransform_XSLTC#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslTransform_XSLTC/CS/XslTransform_XSLTC.cs#1)]
[!code-vb[XslTransform_XSLTC#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslTransform_XSLTC/VB/XslTransform_XSLTC.vb#1)]  
  
<span data-ttu-id="ceb0b-118">Wenn Sie eine dynamische Verknüpfung zur kompilierten Assembly herstellen möchten, ersetzen Sie im Beispiel oben</span><span class="sxs-lookup"><span data-stu-id="ceb0b-118">To dynamically link to the compiled assembly, replace</span></span>
  
```csharp  
xslt.Load(typeof(Transform));  
```  
  
<span data-ttu-id="ceb0b-119">mit</span><span class="sxs-lookup"><span data-stu-id="ceb0b-119">with</span></span>  
  
```csharp 
xslt.Load(System.Reflection.Assembly.Load("Transform").GetType("Transform"));  
``` 
  
<span data-ttu-id="ceb0b-120">im oben aufgeführten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-120">in the example above.</span></span> <span data-ttu-id="ceb0b-121">Weitere Informationen zur Assembly. Load-Methode finden Sie unter <xref:System.Reflection.Assembly.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="ceb0b-121">For more information on the Assembly.Load method, see <xref:System.Reflection.Assembly.Load%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb0b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceb0b-122">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="ceb0b-123">XSLT-Compiler („xsltc.exe“)</span><span class="sxs-lookup"><span data-stu-id="ceb0b-123">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
- [<span data-ttu-id="ceb0b-124">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="ceb0b-124">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
- [<span data-ttu-id="ceb0b-125">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="ceb0b-125">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
