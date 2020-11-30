---
title: Auflösen von externen Ressourcen während der XSLT-Verarbeitung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 5d50711eda266cecdb817c778f04aa845fa4c342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686643"
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="83480-102">Auflösen von externen Ressourcen während der XSLT-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="83480-102">Resolving External Resources During XSLT Processing</span></span>

<span data-ttu-id="83480-103">Während einer XSLT-Transformation müssen Sie u. U. mehrmals externe Ressourcen auflösen.</span><span class="sxs-lookup"><span data-stu-id="83480-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="83480-104">Verwenden der XmlResolver-Klasse</span><span class="sxs-lookup"><span data-stu-id="83480-104">Using the XmlResolver Class</span></span>  

 <span data-ttu-id="83480-105">Die <xref:System.Xml.XmlResolver>-Klasse wird zum Auflösen externer Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="83480-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="83480-106">In der folgenden Tabelle wird dargestellt, wann der <xref:System.Xml.XmlResolver> während der XSLT-Verarbeitung aktiv wird.</span><span class="sxs-lookup"><span data-stu-id="83480-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="83480-107">XSLT-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="83480-107">XSLT task</span></span>|<span data-ttu-id="83480-108">Verwendung von "XmlResolver"</span><span class="sxs-lookup"><span data-stu-id="83480-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="83480-109">Kompilieren des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="83480-109">Compile the style sheet.</span></span>|<span data-ttu-id="83480-110">Auflösen des URI des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="83480-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="83480-111">- und -</span><span class="sxs-lookup"><span data-stu-id="83480-111">-and-</span></span><br /><br /> <span data-ttu-id="83480-112">Auflösen von URI-Verweisen in allen `xsl:import`-Elementen oder `xsl:include`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="83480-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="83480-113">Ausführen des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="83480-113">Execute the style sheet.</span></span>|<span data-ttu-id="83480-114">Auflösen des URI des Kontextmenüs.</span><span class="sxs-lookup"><span data-stu-id="83480-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="83480-115">- und -</span><span class="sxs-lookup"><span data-stu-id="83480-115">-and-</span></span><br /><br /> <span data-ttu-id="83480-116">Auflösen von URI-Verweisen in beliebigen Funktionen von XSLT-`document()`.</span><span class="sxs-lookup"><span data-stu-id="83480-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="83480-117">Die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode und die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode enthalten Überladungen, die ein <xref:System.Xml.XmlResolver>-Objekt als eines ihrer Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="83480-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="83480-118">Wenn kein <xref:System.Xml.XmlResolver> angegeben ist, wird ein Standard-<xref:System.Xml.XmlUrlResolver> ohne Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="83480-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="83480-119">In der folgenden Liste wird erläutert, wann ein <xref:System.Xml.XmlResolver>-Objekt angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="83480-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
- <span data-ttu-id="83480-120">Wenn der XSLT-Vorgang auf eine Netzwerkressource zugreifen muss, die eine Authentifizierung erfordert, können Sie einen <xref:System.Xml.XmlResolver> mit den notwendigen Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="83480-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
- <span data-ttu-id="83480-121">Wenn Sie die Ressourcen einschränken möchten, auf die der XSLT-Vorgang zugreifen kann, können Sie einen <xref:System.Xml.XmlSecureResolver> mit den korrekt festgelegten Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="83480-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="83480-122">Verwenden Sie die <xref:System.Xml.XmlSecureResolver>-Klasse, wenn Sie eine Ressource öffnen möchten, die nicht von Ihnen gesteuert wird oder die nicht vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="83480-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
- <span data-ttu-id="83480-123">Wenn Sie das Verhalten anpassen möchten, können Sie eine eigene <xref:System.Xml.XmlResolver>-Klasse implementieren und diese zum Auflösen von Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="83480-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
- <span data-ttu-id="83480-124">Wenn Sie sich vergewissern möchten, dass auf keine externe Ressource zugegriffen wird, können Sie für das `null`-Argument <xref:System.Xml.XmlResolver> angeben.</span><span class="sxs-lookup"><span data-stu-id="83480-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83480-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83480-125">Example</span></span>  

 <span data-ttu-id="83480-126">Im folgenden Beispiel wird ein Stylesheet kompiliert, das in einer Netzwerkressource gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="83480-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="83480-127">Ein <xref:System.Xml.XmlUrlResolver>-Objekt gibt die Anmeldeinformationen an, die für den Zugriff auf das Stylesheet erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="83480-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="83480-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83480-128">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [<span data-ttu-id="83480-129">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="83480-129">XSLT Transformations</span></span>](xslt-transformations.md)
