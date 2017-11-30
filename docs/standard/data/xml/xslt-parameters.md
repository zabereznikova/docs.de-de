---
title: XSLT-Parameter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e66d98501bb0bd3a5d5cd5eacc0b09405c158522
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-parameters"></a><span data-ttu-id="f5f3c-102">XSLT-Parameter</span><span class="sxs-lookup"><span data-stu-id="f5f3c-102">XSLT Parameters</span></span>
<span data-ttu-id="f5f3c-103">XSLT-Parameter werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-103">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="f5f3c-104">Dabei werden ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-104">A qualified name and namespace URI are associated with the parameter object at that time.</span></span>  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="f5f3c-105">So verwenden Sie einen XSLT-Parameter</span><span class="sxs-lookup"><span data-stu-id="f5f3c-105">To use an XSLT parameter</span></span>  
  
1.  <span data-ttu-id="f5f3c-106">Erstellen Sie ein <xref:System.Xml.Xsl.XsltArgumentList>-Objekt, und fügen Sie den Parameter mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-106">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the parameter using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span>  
  
2.  <span data-ttu-id="f5f3c-107">Rufen Sie den Parameter aus dem Stylesheet auf.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-107">Call the parameter from the style sheet.</span></span>  
  
3.  <span data-ttu-id="f5f3c-108">Übergeben Sie das <xref:System.Xml.Xsl.XsltArgumentList>-Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-108">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="parameter-types"></a><span data-ttu-id="f5f3c-109">Parametertypen</span><span class="sxs-lookup"><span data-stu-id="f5f3c-109">Parameter Types</span></span>  
 <span data-ttu-id="f5f3c-110">Das Parameterobjekt sollte einem W3C-Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-110">The parameter object should correspond to a W3C type.</span></span> <span data-ttu-id="f5f3c-111">In der folgenden Tabelle sind die jeweiligen W3C-Typen mit den entsprechenden Microsoft .NET-Klassen (Typen) aufgelistet. Weiterhin wird angegeben, ob es sich bei dem W3C-Typ um einen XPath-Typ oder einen XSLT-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-111">The following table shows the corresponding W3C types, the equivalent Microsoft .NET classes (type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="f5f3c-112">W3C-Typ</span><span class="sxs-lookup"><span data-stu-id="f5f3c-112">W3C type</span></span>|<span data-ttu-id="f5f3c-113">Entsprechende .NET-Klasse (Typ)</span><span class="sxs-lookup"><span data-stu-id="f5f3c-113">Equivalent .NET class (type)</span></span>|<span data-ttu-id="f5f3c-114">XPath-Typ oder XSLT-Typ</span><span class="sxs-lookup"><span data-stu-id="f5f3c-114">XPath or XSLT type</span></span>|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="f5f3c-115">XPath</span><span class="sxs-lookup"><span data-stu-id="f5f3c-115">XPath</span></span>|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="f5f3c-116">XPath</span><span class="sxs-lookup"><span data-stu-id="f5f3c-116">XPath</span></span>|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="f5f3c-117">XPath</span><span class="sxs-lookup"><span data-stu-id="f5f3c-117">XPath</span></span>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="f5f3c-118">XSLT</span><span class="sxs-lookup"><span data-stu-id="f5f3c-118">XSLT</span></span>|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="f5f3c-119">XPath</span><span class="sxs-lookup"><span data-stu-id="f5f3c-119">XPath</span></span>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> <span data-ttu-id="f5f3c-120">**XPathNavigator]**</span><span class="sxs-lookup"><span data-stu-id="f5f3c-120">**XPathNavigator[]**</span></span>|<span data-ttu-id="f5f3c-121">XPath</span><span class="sxs-lookup"><span data-stu-id="f5f3c-121">XPath</span></span>|  
  
 <span data-ttu-id="f5f3c-122">*Dies entspricht einer Knotengruppe, die einen Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-122">*This is equivalent to a node set that contains a single node.</span></span>  
  
 <span data-ttu-id="f5f3c-123">Wenn das Parameterobjekt keiner der oben genannten Klassen entspricht, wird es entsprechend der folgenden Regeln konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-123">If the parameter object is not one of the above classes, it is converted according to the following rules.</span></span> <span data-ttu-id="f5f3c-124">Numerische CLR-Typen (Common Language Runtime) werden in <xref:System.Double> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-124">Common language runtime (CLR) numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="f5f3c-125">Der <xref:System.DateTime>-Typ wird in <xref:System.String> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-125">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="f5f3c-126"><xref:System.Xml.XPath.IXPathNavigable>-Typen werden in <xref:System.Xml.XPath.XPathNavigator> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-126"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="f5f3c-127">**XPathNavigator []** konvertiert <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-127">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="f5f3c-128">Alle anderen Typen lösen einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-128">All other types throw an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5f3c-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5f3c-129">Example</span></span>  
 <span data-ttu-id="f5f3c-130">Im folgenden Beispiel wird mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode ein Parameter erstellt, der ein berechnetes Skontodatum enthält.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-130">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold calculated discount date.</span></span> <span data-ttu-id="f5f3c-131">Das Skontodatum ist 20 Tage nach dem Auftragsdatum.</span><span class="sxs-lookup"><span data-stu-id="f5f3c-131">The discount date is calculated to be 20 days from the order date.</span></span>  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="f5f3c-132">Eingabe</span><span class="sxs-lookup"><span data-stu-id="f5f3c-132">Input</span></span>  
  
##### <a name="orderxml"></a><span data-ttu-id="f5f3c-133">order.xml</span><span class="sxs-lookup"><span data-stu-id="f5f3c-133">order.xml</span></span>  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a><span data-ttu-id="f5f3c-134">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="f5f3c-134">discount.xsl</span></span>  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="f5f3c-135">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f5f3c-135">Output</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5f3c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5f3c-136">See Also</span></span>  
 [<span data-ttu-id="f5f3c-137">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="f5f3c-137">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
