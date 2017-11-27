---
title: GetXmlNamespace-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47ba67bc58debf8f144f6468bf510932414c0698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="bd440-102">GetXmlNamespace-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd440-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="bd440-103">Ruft die <xref:System.Xml.Linq.XNamespace> Objekt, das das angegebene XML-Namespacepräfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="bd440-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd440-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd440-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="bd440-105">Teile</span><span class="sxs-lookup"><span data-stu-id="bd440-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="bd440-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd440-106">Optional.</span></span> <span data-ttu-id="bd440-107">Die Zeichenfolge, die das XML-Namespacepräfix identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bd440-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="bd440-108">Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="bd440-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="bd440-109">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="bd440-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="bd440-110">Wenn kein Präfix angegeben ist, wird der Standardnamespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd440-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="bd440-111">Wenn kein Standardnamespace angegeben ist, wird der leere Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd440-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd440-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bd440-112">Return Value</span></span>  
 <span data-ttu-id="bd440-113">Die <xref:System.Xml.Linq.XNamespace> Objekt, das das XML-Namespacepräfix entspricht.</span><span class="sxs-lookup"><span data-stu-id="bd440-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd440-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd440-114">Remarks</span></span>  
 <span data-ttu-id="bd440-115">Die `GetXmlNamespace` Operator Ruft die <xref:System.Xml.Linq.XNamespace> Objekt, das das XML-Namespacepräfix entspricht `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="bd440-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="bd440-116">Sie können XML-Namespacepräfixe direkt im XML-Literale und XML-Achseneigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd440-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="bd440-117">Allerdings müssen Sie mithilfe der `GetXmlNamespace` Operator, um ein Namespacepräfix zu konvertieren einer <xref:System.Xml.Linq.XNamespace> Objekt, bevor Sie es in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bd440-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="bd440-118">Können Sie einen nicht qualifizierten Elementnamen zum Anfügen einer <xref:System.Xml.Linq.XNamespace> einen vollqualifizierten abzurufenden Objekts <xref:System.Xml.Linq.XName> -Objekt, das für viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methoden erfordern.</span><span class="sxs-lookup"><span data-stu-id="bd440-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd440-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd440-119">Example</span></span>  
 <span data-ttu-id="bd440-120">Im folgenden Beispiel wird importiert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="bd440-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="bd440-121">Es verwendet dann das Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="bd440-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="bd440-122">Es übergibt dann diese untergeordneten Knoten, der die `ShowName` -Unterroutine, die mit einen qualifizierten Namen erstellt die `GetXmlNamespace` Operator.</span><span class="sxs-lookup"><span data-stu-id="bd440-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="bd440-123">Die `ShowName` Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A> Methode zum Abrufen der übergeordneten `ns:contact` Knoten.</span><span class="sxs-lookup"><span data-stu-id="bd440-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 <span data-ttu-id="bd440-124">Beim Aufruf `TestGetXmlNamespace.RunSample()`, es wird ein Meldungsfeld mit dem folgenden Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd440-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="bd440-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd440-125">See Also</span></span>  
 [<span data-ttu-id="bd440-126">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="bd440-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="bd440-127">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd440-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
