---
title: 'Vorgehensweise: Konfigurieren einer Anwendungsdomäne'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe0c7ecf1b0daf0e9ea56ec590083fe1ccd2d693
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225078"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="9a79c-102">Vorgehensweise: Konfigurieren einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="9a79c-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="9a79c-103">Sie können die Common Language Runtime mit Konfigurationsinformationen mithilfe der <xref:System.AppDomainSetup>-Klasse für eine Anwendungsdomäne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9a79c-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="9a79c-104">Wenn Sie Ihre eigenen Anwendungsdomänen erstellen, ist die wichtigste Eigenschaft <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a79c-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="9a79c-105">Die anderen **AppDomainSetup**-Eigenschaften werden hauptsächlich von den Runtimehosts zur Konfiguration einer bestimmten Anwendungsdomäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a79c-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="9a79c-106">Die Eigenschaft **ApplicationBase** definiert das Stammverzeichnis der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9a79c-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="9a79c-107">Wenn die Runtime eine Typanforderung erfüllen muss, sucht sie nach der Assembly, die den Typ im Verzeichnis enthält, der von der **ApplicationBase**-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9a79c-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a79c-108">Eine neue Anwendungsdomäne erbt nur die **ApplicationBase**-Eigenschaft des Erstellers.</span><span class="sxs-lookup"><span data-stu-id="9a79c-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="9a79c-109">Das folgende Beispiel erstellt eine Instanz der **AppDomainSetup**-Klasse, verwendet diese Klasse, um eine neue Anwendungsdomäne zu erstellen, schreibt die Informationen in die Konsole und entlädt die Anwendungsdomäne anschließend.</span><span class="sxs-lookup"><span data-stu-id="9a79c-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a79c-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a79c-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9a79c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a79c-111">See also</span></span>

- [<span data-ttu-id="9a79c-112">Programmieren mit Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="9a79c-112">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="9a79c-113">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="9a79c-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
