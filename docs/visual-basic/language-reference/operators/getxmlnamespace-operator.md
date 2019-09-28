---
title: GetXmlNamespace-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592164"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="316a3-102">GetXmlNamespace-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="316a3-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="316a3-103">Ruft das <xref:System.Xml.Linq.XNamespace>-Objekt ab, das dem angegebenen XML-Namespace Präfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="316a3-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="316a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="316a3-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="316a3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="316a3-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="316a3-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="316a3-106">Optional.</span></span> <span data-ttu-id="316a3-107">Die Zeichenfolge, die das XML-Namespace Präfix identifiziert.</span><span class="sxs-lookup"><span data-stu-id="316a3-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="316a3-108">Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="316a3-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="316a3-109">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="316a3-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="316a3-110">Wenn kein Präfix angegeben wird, wird der Standard Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="316a3-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="316a3-111">Wenn kein Standard Namespace angegeben wird, wird der leere Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="316a3-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="316a3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="316a3-112">Return Value</span></span>  
 <span data-ttu-id="316a3-113">Das <xref:System.Xml.Linq.XNamespace>-Objekt, das dem XML-Namespace Präfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="316a3-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="316a3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="316a3-114">Remarks</span></span>  
 <span data-ttu-id="316a3-115">Der `GetXmlNamespace`-Operator Ruft das <xref:System.Xml.Linq.XNamespace>-Objekt ab, das dem XML-Namespace Präfix `xmlNamespacePrefix` entspricht.</span><span class="sxs-lookup"><span data-stu-id="316a3-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="316a3-116">Sie können XML-Namespace Präfixe direkt in XML-Literalen und XML-Achsen Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="316a3-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="316a3-117">Allerdings müssen Sie den `GetXmlNamespace`-Operator verwenden, um ein Namespace Präfix in ein <xref:System.Xml.Linq.XNamespace>-Objekt zu konvertieren, bevor Sie es in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="316a3-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="316a3-118">Sie können einen nicht qualifizierten Elementnamen an ein <xref:System.Xml.Linq.XNamespace>-Objekt anfügen, um ein voll qualifizierter <xref:System.Xml.Linq.XName>-Objekt zu erhalten, das viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Methoden erfordern.</span><span class="sxs-lookup"><span data-stu-id="316a3-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="316a3-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="316a3-119">Example</span></span>  
 <span data-ttu-id="316a3-120">Im folgenden Beispiel wird `ns` als XML-Namespace Präfix importiert.</span><span class="sxs-lookup"><span data-stu-id="316a3-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="316a3-121">Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone` zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="316a3-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="316a3-122">Er übergibt dann diesen untergeordneten Knoten an die `ShowName`-Unterroutine, die mithilfe des `GetXmlNamespace`-Operators einen qualifizierten Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="316a3-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="316a3-123">Die `ShowName`-Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A>-Methode, um den übergeordneten `ns:contact`-Knoten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="316a3-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="316a3-124">Wenn Sie `TestGetXmlNamespace.RunSample()` aufzurufen, wird ein Meldungs Feld angezeigt, das den folgenden Text enthält:</span><span class="sxs-lookup"><span data-stu-id="316a3-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="316a3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="316a3-125">See also</span></span>

- [<span data-ttu-id="316a3-126">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="316a3-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="316a3-127">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="316a3-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
