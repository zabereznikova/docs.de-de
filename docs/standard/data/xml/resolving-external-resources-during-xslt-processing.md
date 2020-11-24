---
title: Auflösen von externen Ressourcen während der XSLT-Verarbeitung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 67c25015f1127a62c480a8fc09c5945682097124
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823679"
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="1d717-102">Auflösen von externen Ressourcen während der XSLT-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="1d717-102">Resolving External Resources During XSLT Processing</span></span>
<span data-ttu-id="1d717-103">Während einer XSLT-Transformation müssen Sie u. U. mehrmals externe Ressourcen auflösen.</span><span class="sxs-lookup"><span data-stu-id="1d717-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="1d717-104">Verwenden der XmlResolver-Klasse</span><span class="sxs-lookup"><span data-stu-id="1d717-104">Using the XmlResolver Class</span></span>  
 <span data-ttu-id="1d717-105">Die <xref:System.Xml.XmlResolver>-Klasse wird zum Auflösen externer Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d717-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="1d717-106">In der folgenden Tabelle wird dargestellt, wann der <xref:System.Xml.XmlResolver> während der XSLT-Verarbeitung aktiv wird.</span><span class="sxs-lookup"><span data-stu-id="1d717-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="1d717-107">XSLT-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="1d717-107">XSLT task</span></span>|<span data-ttu-id="1d717-108">Verwendung von "XmlResolver"</span><span class="sxs-lookup"><span data-stu-id="1d717-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="1d717-109">Kompilieren des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="1d717-109">Compile the style sheet.</span></span>|<span data-ttu-id="1d717-110">Auflösen des URI des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="1d717-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="1d717-111">- und -</span><span class="sxs-lookup"><span data-stu-id="1d717-111">-and-</span></span><br /><br /> <span data-ttu-id="1d717-112">Auflösen von URI-Verweisen in allen `xsl:import`-Elementen oder `xsl:include`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="1d717-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="1d717-113">Ausführen des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="1d717-113">Execute the style sheet.</span></span>|<span data-ttu-id="1d717-114">Auflösen des URI des Kontextmenüs.</span><span class="sxs-lookup"><span data-stu-id="1d717-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="1d717-115">- und -</span><span class="sxs-lookup"><span data-stu-id="1d717-115">-and-</span></span><br /><br /> <span data-ttu-id="1d717-116">Auflösen von URI-Verweisen in beliebigen Funktionen von XSLT-`document()`.</span><span class="sxs-lookup"><span data-stu-id="1d717-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="1d717-117">Die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode und die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode enthalten Überladungen, die ein <xref:System.Xml.XmlResolver>-Objekt als eines ihrer Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d717-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="1d717-118">Wenn kein <xref:System.Xml.XmlResolver> angegeben ist, wird ein Standard-<xref:System.Xml.XmlUrlResolver> ohne Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d717-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="1d717-119">In der folgenden Liste wird erläutert, wann ein <xref:System.Xml.XmlResolver>-Objekt angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d717-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
- <span data-ttu-id="1d717-120">Wenn der XSLT-Vorgang auf eine Netzwerkressource zugreifen muss, die eine Authentifizierung erfordert, können Sie einen <xref:System.Xml.XmlResolver> mit den notwendigen Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d717-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
- <span data-ttu-id="1d717-121">Wenn Sie die Ressourcen einschränken möchten, auf die der XSLT-Vorgang zugreifen kann, können Sie einen <xref:System.Xml.XmlSecureResolver> mit den korrekt festgelegten Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d717-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="1d717-122">Verwenden Sie die <xref:System.Xml.XmlSecureResolver>-Klasse, wenn Sie eine Ressource öffnen möchten, die nicht von Ihnen gesteuert wird oder die nicht vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="1d717-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
- <span data-ttu-id="1d717-123">Wenn Sie das Verhalten anpassen möchten, können Sie eine eigene <xref:System.Xml.XmlResolver>-Klasse implementieren und diese zum Auflösen von Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d717-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
- <span data-ttu-id="1d717-124">Wenn Sie sich vergewissern möchten, dass auf keine externe Ressource zugegriffen wird, können Sie für das `null`-Argument <xref:System.Xml.XmlResolver> angeben.</span><span class="sxs-lookup"><span data-stu-id="1d717-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d717-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d717-125">Example</span></span>  
 <span data-ttu-id="1d717-126">Im folgenden Beispiel wird ein Stylesheet kompiliert, das in einer Netzwerkressource gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="1d717-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="1d717-127">Ein <xref:System.Xml.XmlUrlResolver>-Objekt gibt die Anmeldeinformationen an, die für den Zugriff auf das Stylesheet erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1d717-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="1d717-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d717-128">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [<span data-ttu-id="1d717-129">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="1d717-129">XSLT Transformations</span></span>](xslt-transformations.md)
