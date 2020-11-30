---
title: XSLT-Erweiterungsobjekte
ms.date: 03/30/2017
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
ms.openlocfilehash: 0e874bb7679854b75a07eb452e47eba0d30807a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720788"
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="ffb69-102">XSLT-Erweiterungsobjekte</span><span class="sxs-lookup"><span data-stu-id="ffb69-102">XSLT Extension Objects</span></span>

<span data-ttu-id="ffb69-103">Mit Erweiterungsobjekten kann der Funktionsumfang von Stylesheets erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="ffb69-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="ffb69-104">Erweiterungsobjekte werden von der <xref:System.Xml.Xsl.XsltArgumentList>-Klasse beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ffb69-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="ffb69-105">Die Verwendung eines Erweiterungsobjekts bietet gegenüber der Verwendung eines eingebetteten Skripts folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="ffb69-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
- <span data-ttu-id="ffb69-106">Sie ermöglicht eine bessere Kapselung und Wiederverwendung von Klassen.</span><span class="sxs-lookup"><span data-stu-id="ffb69-106">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="ffb69-107">Stylesheets werden kleiner und sind besser verwaltbar.</span><span class="sxs-lookup"><span data-stu-id="ffb69-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="ffb69-108">XSLT-Erweiterungsobjekte werden dem <xref:System.Xml.Xsl.XsltArgumentList>-Objekt mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ffb69-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="ffb69-109">Dabei wird ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.</span><span class="sxs-lookup"><span data-stu-id="ffb69-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ffb69-110">Um die <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode aufzurufen, muss die FullTrust-Berechtigung festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="ffb69-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="ffb69-111">Weitere Informationen finden Sie unter [Codezugriffssicherheit](../../../framework/misc/code-access-security.md) und [Benannte Berechtigungssätze](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ffb69-111">For more information, see [Code Access Security](../../../framework/misc/code-access-security.md) and [Named Permission Sets](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="ffb69-112">Von Erweiterungsobjekten kann einer der vier XPath-Grunddatentypen (`number`, `string`, `Boolean` und `node set`) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ffb69-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="ffb69-113">Alle Methoden, die mit dem `params`-Schlüsselwort definiert sind, mit dem eine nicht definierte Anzahl von Parametern übergeben werden kann, werden derzeit nicht von der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ffb69-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="ffb69-114">XSLT-Stylesheets, die Methoden mit dem `params`-Schlüsselwort verwenden, funktionieren nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="ffb69-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="ffb69-115">Einzelheiten finden Sie unter [params](../../../csharp/language-reference/keywords/params.md).</span><span class="sxs-lookup"><span data-stu-id="ffb69-115">For details, see [params](../../../csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="ffb69-116">So verwenden Sie ein XSLT-Erweiterungsobjekt</span><span class="sxs-lookup"><span data-stu-id="ffb69-116">To use an XSLT extension object</span></span>  
  
1. <span data-ttu-id="ffb69-117">Erstellen Sie ein <xref:System.Xml.Xsl.XsltArgumentList>-Objekt, und fügen Sie das Erweiterungsobjekt mit der <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="ffb69-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2. <span data-ttu-id="ffb69-118">Rufen Sie das Erweiterungsobjekt aus dem Stylesheet auf.</span><span class="sxs-lookup"><span data-stu-id="ffb69-118">Call the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="ffb69-119">Übergeben Sie das <xref:System.Xml.Xsl.XsltArgumentList>-Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="ffb69-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb69-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffb69-120">See also</span></span>

- [<span data-ttu-id="ffb69-121">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="ffb69-121">XSLT Transformations</span></span>](xslt-transformations.md)
- [<span data-ttu-id="ffb69-122">XSLT-Sicherheitsaspekte</span><span class="sxs-lookup"><span data-stu-id="ffb69-122">XSLT Security Considerations</span></span>](xslt-security-considerations.md)
