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
ms.openlocfilehash: f9201aa4b2aa9280b9b3a4e0a2badf25ea819088
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684748"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="44db3-102">GetXmlNamespace-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44db3-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="44db3-103">Ruft die <xref:System.Xml.Linq.XNamespace> Objekt, das dem angegebenen XML-Namespacepräfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="44db3-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44db3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44db3-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="44db3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="44db3-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="44db3-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="44db3-106">Optional.</span></span> <span data-ttu-id="44db3-107">Die Zeichenfolge, die das XML-Namespacepräfix identifiziert.</span><span class="sxs-lookup"><span data-stu-id="44db3-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="44db3-108">Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="44db3-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="44db3-109">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="44db3-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="44db3-110">Wenn kein Präfix angegeben ist, wird der Standardnamespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44db3-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="44db3-111">Wenn kein Standardnamespace angegeben wird, wird der leere Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44db3-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44db3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="44db3-112">Return Value</span></span>  
 <span data-ttu-id="44db3-113">Die <xref:System.Xml.Linq.XNamespace> Objekt, das das XML-Namespacepräfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="44db3-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44db3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44db3-114">Remarks</span></span>  
 <span data-ttu-id="44db3-115">Die `GetXmlNamespace` Operator Ruft die <xref:System.Xml.Linq.XNamespace> Objekt, das das XML-Namespacepräfix entspricht `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="44db3-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="44db3-116">Sie können XML-Namespacepräfixe direkt in XML-Literale und XML-Achseneigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="44db3-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="44db3-117">Allerdings müssen Sie verwenden die `GetXmlNamespace` Operator, um ein Namespacepräfix zu konvertieren eine <xref:System.Xml.Linq.XNamespace> Objekt, bevor Sie es in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="44db3-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="44db3-118">Können Sie einen nicht qualifizierten Elementnamen zum Anfügen einer <xref:System.Xml.Linq.XNamespace> einen vollqualifizierten abzurufenden Objekts <xref:System.Xml.Linq.XName> Objekt, das für viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methoden erfordern.</span><span class="sxs-lookup"><span data-stu-id="44db3-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44db3-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44db3-119">Example</span></span>  
 <span data-ttu-id="44db3-120">Das folgende Beispiel importiert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="44db3-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="44db3-121">Klicken Sie dann das Namespacepräfix des Namespace eine XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen verwendet `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="44db3-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="44db3-122">Anschließend übergibt es dieses untergeordneten Knotens, der `ShowName` -Unterroutine, die einen qualifizierten Namen erstellt, mit der `GetXmlNamespace` Operator.</span><span class="sxs-lookup"><span data-stu-id="44db3-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="44db3-123">Die `ShowName` Unterroutine übergibt dann den qualifizierten Namen auf die <xref:System.Xml.Linq.XNode.Ancestors%2A> -Methode zum Abrufen der übergeordneten `ns:contact` Knoten.</span><span class="sxs-lookup"><span data-stu-id="44db3-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 <span data-ttu-id="44db3-124">Beim Aufruf `TestGetXmlNamespace.RunSample()`, es wird ein Meldungsfeld mit dem folgenden Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="44db3-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="44db3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44db3-125">See also</span></span>
- [<span data-ttu-id="44db3-126">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="44db3-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="44db3-127">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44db3-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
