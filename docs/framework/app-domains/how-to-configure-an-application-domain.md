---
title: "Gewusst wie: Konfigurieren einer Anwendungsdomäne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4f8c91a11deac63e2ad44628a609ed4ca6501e84
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="5e802-102">Gewusst wie: Konfigurieren einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="5e802-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="5e802-103">Sie können die Common Language Runtime mit Konfigurationsinformationen mithilfe der <xref:System.AppDomainSetup>-Klasse für eine Anwendungsdomäne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5e802-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="5e802-104">Wenn Sie Ihre eigenen Anwendungsdomänen erstellen, ist die wichtigste Eigenschaft <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e802-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="5e802-105">Die anderen **AppDomainSetup**-Eigenschaften werden hauptsächlich von den Runtimehosts zur Konfiguration einer bestimmten Anwendungsdomäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e802-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="5e802-106">Die Eigenschaft **ApplicationBase** definiert das Stammverzeichnis der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5e802-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="5e802-107">Wenn die Runtime eine Typanforderung erfüllen muss, sucht sie nach der Assembly, die den Typ im Verzeichnis enthält, der von der **ApplicationBase**-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5e802-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e802-108">Eine neue Anwendungsdomäne erbt nur die **ApplicationBase**-Eigenschaft des Erstellers.</span><span class="sxs-lookup"><span data-stu-id="5e802-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="5e802-109">Das folgende Beispiel erstellt eine Instanz der **AppDomainSetup**-Klasse, verwendet diese Klasse, um eine neue Anwendungsdomäne zu erstellen, schreibt die Informationen in die Konsole und entlädt die Anwendungsdomäne anschließend.</span><span class="sxs-lookup"><span data-stu-id="5e802-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e802-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e802-110">Example</span></span>  
 <span data-ttu-id="5e802-111">[!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)] [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)] [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="5e802-111">[!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)] [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)] [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e802-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e802-112">See Also</span></span>  
 <span data-ttu-id="5e802-113">[Programmieren mit Anwendungsdomänen](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="5e802-113">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 [<span data-ttu-id="5e802-114">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="5e802-114">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

