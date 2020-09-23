---
title: 'Vorgehensweise: Einbetten von Ausdrücken in XML-Literale'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 5ce1386e6a1ff8ffce296f5cea694499633eb011
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071208"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="0f651-102">Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f651-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="0f651-103">XML-Literale können mit eingebetteten Ausdrücken kombiniert werden, um XML-Dokumente, Fragmente oder Elemente zu erstellen, die zur Laufzeit erstellte Inhalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f651-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="0f651-104">In den folgenden Beispielen wird veranschaulicht, wie eingebettete Ausdrücke verwendet werden, um Elementinhalte, Attribute und Elementnamen zur Laufzeit aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="0f651-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="0f651-105">Die Syntax für einen eingebetteten Ausdruck ist, bei der es sich um `<%=` `exp` `%>` dieselbe Syntax handelt, die von ASP.NET verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f651-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="0f651-106">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0f651-106">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="0f651-107">Sie können auch die- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs verwenden, um-Objekte zu erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f651-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="0f651-108">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0f651-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="0f651-109">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0f651-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="0f651-110">So fügen Sie Text als Element Inhalt ein</span><span class="sxs-lookup"><span data-stu-id="0f651-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="0f651-111">Im folgenden Beispiel wird gezeigt, wie der in der-Variable enthaltene Text `contactName` zwischen den öffnenden und schließenden namens Elementen eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0f651-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="0f651-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0f651-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="0f651-113">So fügen Sie Text als Attribut Wert ein</span><span class="sxs-lookup"><span data-stu-id="0f651-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="0f651-114">Im folgenden Beispiel wird gezeigt, wie der in der-Variablen enthaltene Text `phoneType` als Wert des- `type` Attributs eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0f651-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="0f651-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0f651-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="0f651-116">So fügen Sie Text für einen Elementnamen ein</span><span class="sxs-lookup"><span data-stu-id="0f651-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="0f651-117">Im folgenden Beispiel wird gezeigt, wie der in der Variablen enthaltene Text `elementName` als Name eines Elements eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0f651-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="0f651-118">Wenn Sie Elemente mit dieser Technik erstellen, müssen Sie Sie mit dem- \</> Tag schließen.</span><span class="sxs-lookup"><span data-stu-id="0f651-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="0f651-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0f651-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0f651-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f651-120">See also</span></span>

- [<span data-ttu-id="0f651-121">Vorgehensweise: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="0f651-121">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)
- [<span data-ttu-id="0f651-122">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="0f651-122">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)
- [<span data-ttu-id="0f651-123">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f651-123">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="0f651-124">XML</span><span class="sxs-lookup"><span data-stu-id="0f651-124">XML</span></span>](index.md)
