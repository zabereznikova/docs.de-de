---
title: '@ServiceHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed64a90131fcd8f2d9f2120c03db4a21d8dc6efe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="servicehost"></a>@ServiceHost
<span data-ttu-id="d27c5-101">Ordnet die Factory zu, die zum Generieren des Diensthosts mit dem zu hostenden Dienst verwendet wird, sowie andere Programmieraspekte, die für den Zugriff und die Kompilierung des in der SVC-Datei enthaltenen Hostingcodes erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d27c5-101">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d27c5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="d27c5-102">Syntax</span></span>  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a><span data-ttu-id="d27c5-103">Attribute</span><span class="sxs-lookup"><span data-stu-id="d27c5-103">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="d27c5-104">Dienst</span><span class="sxs-lookup"><span data-stu-id="d27c5-104">Service</span></span>  
 <span data-ttu-id="d27c5-105">Der CLR-Typname des gehosteten Diensts.</span><span class="sxs-lookup"><span data-stu-id="d27c5-105">The CLR type name of the service hosted.</span></span> <span data-ttu-id="d27c5-106">Dabei sollte es sich um einen qualifizierten Namen eines Typs handeln, der mindestens einen Dienstkontakt implementiert.</span><span class="sxs-lookup"><span data-stu-id="d27c5-106">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="d27c5-107">Factory</span><span class="sxs-lookup"><span data-stu-id="d27c5-107">Factory</span></span>  
 <span data-ttu-id="d27c5-108">Der CLR-Typname der Diensthostfactory, der zum Instanziieren des Diensthosts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d27c5-108">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="d27c5-109">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="d27c5-109">This attribute is optional.</span></span> <span data-ttu-id="d27c5-110">Falls nicht angegeben, wird die Standard-<xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d27c5-110">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="d27c5-111">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d27c5-111">Debug</span></span>  
 <span data-ttu-id="d27c5-112">Gibt an, ob der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst mit Debugsymbolen kompiliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d27c5-112">Indicates whether the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service should be compiled with debug symbols.</span></span> <span data-ttu-id="d27c5-113">Lautet `true`, wenn der [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienst mit Debugsymbolen kompiliert werden soll, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d27c5-113">`true` if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="d27c5-114">Sprache</span><span class="sxs-lookup"><span data-stu-id="d27c5-114">Language</span></span>  
 <span data-ttu-id="d27c5-115">Gibt die Sprache zum Kompilieren des gesamten Inlinecodes in der Datei (SVC) an.</span><span class="sxs-lookup"><span data-stu-id="d27c5-115">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="d27c5-116">Die Werte können jede von .NET unterstützte Sprache darstellen, darunter C#, VB und JS, die sich jeweils auf C#, Visual Basic .NET und JScript .NET beziehen.</span><span class="sxs-lookup"><span data-stu-id="d27c5-116">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="d27c5-117">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="d27c5-117">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="d27c5-118">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="d27c5-118">CodeBehind</span></span>  
 <span data-ttu-id="d27c5-119">Gibt die Quelldatei an, die den XML-Webdienst implementiert, wenn sich die Klasse, die den XML-Webdienst implementiert, nicht in derselben Datei befindet und nicht in eine Assembly kompiliert oder im Verzeichnis \Bin gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="d27c5-119">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d27c5-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d27c5-120">Remarks</span></span>  
 <span data-ttu-id="d27c5-121">Der <xref:System.ServiceModel.ServiceHost>, der verwendet wird, um den Dienst zu hosten, ist ein Aspekt der Erweiterbarkeit innerhalb des [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Programmiermodells.</span><span class="sxs-lookup"><span data-stu-id="d27c5-121">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] programming model.</span></span> <span data-ttu-id="d27c5-122">Ein Factorymuster wird zum Instanziieren von <xref:System.ServiceModel.ServiceHost> verwendet, da es sich möglicherweise um einen polymorphen Typ handelt, der von der Hostumgebung nicht direkt instanziiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="d27c5-122">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="d27c5-123">Die Standardimplementierung verwendet <xref:System.ServiceModel.Activation.ServiceHostFactory>, um eine Instanz von <xref:System.ServiceModel.ServiceHost> zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d27c5-123">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d27c5-124">Aber Sie können eine eigene Factory (eine, die den abgeleiteten Host zurückgibt) Geben Sie dazu die CLR-Typnamen Ihrer Factory-Implementierung in der [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="d27c5-124">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="d27c5-125">Wenn Sie eigene benutzerdefinierte Diensthostfactory statt der standardfactory verwenden möchten, geben Sie nur den Typnamen in der [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d27c5-125">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="d27c5-126">Halten Sie die Factoryimplementierungen so einfach wie möglich.</span><span class="sxs-lookup"><span data-stu-id="d27c5-126">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="d27c5-127">Falls die benutzerdefinierte Logik umfassend ist, kann der Code einfacher wiederverwendet werden, wenn Sie diese Logik im Host und nicht in der Factory platzieren.</span><span class="sxs-lookup"><span data-stu-id="d27c5-127">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="d27c5-128">Beispielsweise, um einen AJAX-aktivierten Endpunkt für aktivieren `MyService`, geben Sie die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> für den Wert des der `Factory` -Attribut, anstelle des standardmäßigen <xref:System.ServiceModel.Activation.ServiceHostFactory>in der [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) als Richtlinie Im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d27c5-128">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d27c5-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d27c5-129">Example</span></span>  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d27c5-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d27c5-130">See Also</span></span>  
 [<span data-ttu-id="d27c5-131">Benutzerdefinierter Diensthost</span><span class="sxs-lookup"><span data-stu-id="d27c5-131">Custom Service Host</span></span>](../../../../../docs/framework/wcf/samples/custom-service-host.md)
