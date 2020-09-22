---
title: GetXmlNamespace-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 660474c1193076755889fd885c1b78bec78f0a2c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873475"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="6898e-102">GetXmlNamespace-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6898e-102">GetXmlNamespace Operator (Visual Basic)</span></span>

<span data-ttu-id="6898e-103">Ruft das- <xref:System.Xml.Linq.XNamespace> Objekt ab, das dem angegebenen XML-Namespace Präfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="6898e-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6898e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6898e-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="6898e-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="6898e-105">Parts</span></span>  

 `xmlNamespacePrefix`  
 <span data-ttu-id="6898e-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="6898e-106">Optional.</span></span> <span data-ttu-id="6898e-107">Die Zeichenfolge, die das XML-Namespace Präfix identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6898e-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="6898e-108">Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="6898e-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="6898e-109">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6898e-109">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="6898e-110">Wenn kein Präfix angegeben wird, wird der Standard Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6898e-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="6898e-111">Wenn kein Standard Namespace angegeben wird, wird der leere Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6898e-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6898e-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6898e-112">Return Value</span></span>  

 <span data-ttu-id="6898e-113">Das- <xref:System.Xml.Linq.XNamespace> Objekt, das dem XML-Namespace Präfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="6898e-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6898e-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6898e-114">Remarks</span></span>  

 <span data-ttu-id="6898e-115">Der- `GetXmlNamespace` Operator Ruft das-Objekt ab <xref:System.Xml.Linq.XNamespace> , das dem XML-Namespace Präfix entspricht `xmlNamespacePrefix` .</span><span class="sxs-lookup"><span data-stu-id="6898e-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="6898e-116">Sie können XML-Namespace Präfixe direkt in XML-Literalen und XML-Achsen Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="6898e-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="6898e-117">Allerdings müssen Sie den- `GetXmlNamespace` Operator verwenden, um ein Namespace Präfix in ein Objekt zu konvertieren, <xref:System.Xml.Linq.XNamespace> bevor Sie es in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6898e-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="6898e-118">Sie können einen nicht qualifizierten Elementnamen an ein Objekt anfügen, <xref:System.Xml.Linq.XNamespace> um ein voll qualifizierter Objekt zu erhalten <xref:System.Xml.Linq.XName> , das viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methoden erfordert.</span><span class="sxs-lookup"><span data-stu-id="6898e-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6898e-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6898e-119">Example</span></span>  

 <span data-ttu-id="6898e-120">Im folgenden Beispiel wird `ns` als XML-Namespace Präfix importiert.</span><span class="sxs-lookup"><span data-stu-id="6898e-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="6898e-121">Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen zuzugreifen `ns:phone` .</span><span class="sxs-lookup"><span data-stu-id="6898e-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="6898e-122">Er übergibt dann diesen untergeordneten Knoten an die `ShowName` Unterroutine, die mithilfe des-Operators einen qualifizierten Namen erstellt `GetXmlNamespace` .</span><span class="sxs-lookup"><span data-stu-id="6898e-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="6898e-123">Die `ShowName` Unterroutine übergibt dann den qualifizierten Namen an die- <xref:System.Xml.Linq.XNode.Ancestors%2A> Methode, um den übergeordneten Knoten zu erhalten `ns:contact` .</span><span class="sxs-lookup"><span data-stu-id="6898e-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="6898e-124">Wenn Sie den Befehl ausführen `TestGetXmlNamespace.RunSample()` , wird ein Meldungs Feld angezeigt, das den folgenden Text enthält:</span><span class="sxs-lookup"><span data-stu-id="6898e-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="6898e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6898e-125">See also</span></span>

- [<span data-ttu-id="6898e-126">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="6898e-126">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="6898e-127">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6898e-127">Accessing XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/accessing-xml.md)
