---
title: XSLT-Parameter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
ms.openlocfilehash: 64a62840594773270a658738120812c59b4896cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685213"
---
# <a name="xslt-parameters"></a><span data-ttu-id="58920-102">XSLT-Parameter</span><span class="sxs-lookup"><span data-stu-id="58920-102">XSLT Parameters</span></span>

<span data-ttu-id="58920-103">XSLT-Parameter werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="58920-103">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="58920-104">Dabei werden ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.</span><span class="sxs-lookup"><span data-stu-id="58920-104">A qualified name and namespace URI are associated with the parameter object at that time.</span></span>  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="58920-105">So verwenden Sie einen XSLT-Parameter</span><span class="sxs-lookup"><span data-stu-id="58920-105">To use an XSLT parameter</span></span>  
  
1. <span data-ttu-id="58920-106">Erstellen Sie ein <xref:System.Xml.Xsl.XsltArgumentList>-Objekt, und fügen Sie den Parameter mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="58920-106">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the parameter using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span>  
  
2. <span data-ttu-id="58920-107">Rufen Sie den Parameter aus dem Stylesheet auf.</span><span class="sxs-lookup"><span data-stu-id="58920-107">Call the parameter from the style sheet.</span></span>  
  
3. <span data-ttu-id="58920-108">Übergeben Sie das <xref:System.Xml.Xsl.XsltArgumentList>-Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="58920-108">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="parameter-types"></a><span data-ttu-id="58920-109">Parametertypen</span><span class="sxs-lookup"><span data-stu-id="58920-109">Parameter Types</span></span>  

 <span data-ttu-id="58920-110">Das Parameterobjekt sollte einem W3C-Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="58920-110">The parameter object should correspond to a W3C type.</span></span> <span data-ttu-id="58920-111">In der folgenden Tabelle sind die jeweiligen W3C-Typen mit den entsprechenden Microsoft .NET-Klassen (Typen) aufgelistet. Weiterhin wird angegeben, ob es sich bei dem W3C-Typ um einen XPath-Typ oder einen XSLT-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="58920-111">The following table shows the corresponding W3C types, the equivalent Microsoft .NET classes (type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="58920-112">W3C-Typ</span><span class="sxs-lookup"><span data-stu-id="58920-112">W3C type</span></span>|<span data-ttu-id="58920-113">Entsprechende .NET-Klasse (Typ)</span><span class="sxs-lookup"><span data-stu-id="58920-113">Equivalent .NET class (type)</span></span>|<span data-ttu-id="58920-114">XPath-Typ oder XSLT-Typ</span><span class="sxs-lookup"><span data-stu-id="58920-114">XPath or XSLT type</span></span>|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="58920-115">XPath</span><span class="sxs-lookup"><span data-stu-id="58920-115">XPath</span></span>|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="58920-116">XPath</span><span class="sxs-lookup"><span data-stu-id="58920-116">XPath</span></span>|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="58920-117">XPath</span><span class="sxs-lookup"><span data-stu-id="58920-117">XPath</span></span>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="58920-118">XSLT</span><span class="sxs-lookup"><span data-stu-id="58920-118">XSLT</span></span>|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="58920-119">XPath</span><span class="sxs-lookup"><span data-stu-id="58920-119">XPath</span></span>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> <span data-ttu-id="58920-120">**XPathNavigator[]**</span><span class="sxs-lookup"><span data-stu-id="58920-120">**XPathNavigator[]**</span></span>|<span data-ttu-id="58920-121">XPath</span><span class="sxs-lookup"><span data-stu-id="58920-121">XPath</span></span>|  
  
 <span data-ttu-id="58920-122">\*Dies entspricht einer Knotengruppe, die einen Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="58920-122">\*This is equivalent to a node set that contains a single node.</span></span>  
  
 <span data-ttu-id="58920-123">Wenn das Parameterobjekt keiner der oben genannten Klassen entspricht, wird es entsprechend der folgenden Regeln konvertiert.</span><span class="sxs-lookup"><span data-stu-id="58920-123">If the parameter object is not one of the above classes, it is converted according to the following rules.</span></span> <span data-ttu-id="58920-124">Numerische CLR-Typen (Common Language Runtime) werden in <xref:System.Double> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="58920-124">Common language runtime (CLR) numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="58920-125">Der <xref:System.DateTime>-Typ wird in <xref:System.String> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="58920-125">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="58920-126"><xref:System.Xml.XPath.IXPathNavigable>-Typen werden in <xref:System.Xml.XPath.XPathNavigator> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="58920-126"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="58920-127">**XPathNavigator[]** wird in <xref:System.Xml.XPath.XPathNodeIterator> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="58920-127">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="58920-128">Alle anderen Typen lösen einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="58920-128">All other types throw an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58920-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58920-129">Example</span></span>  

 <span data-ttu-id="58920-130">Im folgenden Beispiel wird mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode ein Parameter erstellt, der ein berechnetes Skontodatum enthält.</span><span class="sxs-lookup"><span data-stu-id="58920-130">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold calculated discount date.</span></span> <span data-ttu-id="58920-131">Das Skontodatum ist 20 Tage nach dem Auftragsdatum.</span><span class="sxs-lookup"><span data-stu-id="58920-131">The discount date is calculated to be 20 days from the order date.</span></span>  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="58920-132">Eingabe</span><span class="sxs-lookup"><span data-stu-id="58920-132">Input</span></span>  
  
##### <a name="orderxml"></a><span data-ttu-id="58920-133">order.xml</span><span class="sxs-lookup"><span data-stu-id="58920-133">order.xml</span></span>  

 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a><span data-ttu-id="58920-134">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="58920-134">discount.xsl</span></span>  

 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="58920-135">Output</span><span class="sxs-lookup"><span data-stu-id="58920-135">Output</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58920-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58920-136">See also</span></span>

- [<span data-ttu-id="58920-137">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="58920-137">XSLT Transformations</span></span>](xslt-transformations.md)
