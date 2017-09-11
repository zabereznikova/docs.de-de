---
title: GetXmlNamespace-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d6f977ab8c0b7dfb2dee936436ef4ec8530ba8f6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="ca11c-102">GetXmlNamespace-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca11c-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="ca11c-103">Ruft die <xref:System.Xml.Linq.XNamespace>Objekt, das dem angegebenen XML-Namespacepräfix entspricht.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="ca11c-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca11c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca11c-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="ca11c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ca11c-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="ca11c-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="ca11c-106">Optional.</span></span> <span data-ttu-id="ca11c-107">Die Zeichenfolge, die das XML-Namespacepräfix identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ca11c-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="ca11c-108">Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="ca11c-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="ca11c-109">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ca11c-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="ca11c-110">Wenn kein Präfix angegeben ist, wird der Standardnamespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ca11c-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="ca11c-111">Wenn kein Standardnamespace angegeben ist, wird der leere Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ca11c-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca11c-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca11c-112">Return Value</span></span>  
 <span data-ttu-id="ca11c-113">Das <xref:System.Xml.Linq.XNamespace>Objekt, das das XML-Namespacepräfix entspricht.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="ca11c-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca11c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca11c-114">Remarks</span></span>  
 <span data-ttu-id="ca11c-115">Die `GetXmlNamespace` Operator Ruft das <xref:System.Xml.Linq.XNamespace>Objekt, das das XML-Namespacepräfix entspricht `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="ca11c-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="ca11c-116">Sie können XML-Namespacepräfixe direkt in XML-Literale und XML-Achseneigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca11c-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="ca11c-117">Allerdings müssen Sie verwenden die `GetXmlNamespace` Operator, um ein Namespacepräfix konvertieren ein <xref:System.Xml.Linq.XNamespace>Objekt, bevor Sie es in Ihrem Code verwenden können.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="ca11c-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="ca11c-118">Können Sie einen nicht qualifizierten Elementnamen zum Anfügen einer <xref:System.Xml.Linq.XNamespace>-Objekts können Sie einen vollqualifizierten abrufen <xref:System.Xml.Linq.XName>-Objekt, das für viele [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Methoden erfordern.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="ca11c-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca11c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca11c-119">Example</span></span>  
 <span data-ttu-id="ca11c-120">Das folgende Beispiel importiert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="ca11c-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="ca11c-121">Anschließend wird mithilfe der Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="ca11c-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="ca11c-122">Anschließend übergibt dieser untergeordnete Knoten an die `ShowName` -Unterroutine, die einen qualifizierten Namen, indem erstellt die `GetXmlNamespace` Operator.</span><span class="sxs-lookup"><span data-stu-id="ca11c-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="ca11c-123">Die `ShowName` -Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A>Methode zum Abrufen der übergeordneten `ns:contact` Knoten.</xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="ca11c-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 <span data-ttu-id="ca11c-124">[!code-vb[VbXMLSamples&#38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ca11c-124">[!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="ca11c-125">Beim Aufruf von `TestGetXmlNamespace.RunSample()`, es wird ein Meldungsfeld mit dem folgenden Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca11c-125">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="ca11c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca11c-126">See Also</span></span>  
 <span data-ttu-id="ca11c-127">[Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="ca11c-127">[Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="ca11c-128"> [Zugreifen auf XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="ca11c-128"> [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span></span>
