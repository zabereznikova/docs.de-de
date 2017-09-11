---
title: "Gewusst wie: Entladen einer Anwendungsdomäne"
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
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eefaf670202e6b4977d75fffa906f1b07053eb3e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="842c9-102">Gewusst wie: Entladen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="842c9-102">How to: Unload an Application Domain</span></span>
<span data-ttu-id="842c9-103">Wenn Sie die Nutzung einer Anwendungsdomäne beenden möchten, entladen Sie sie mithilfe der <xref:System.AppDomain.Unload%2A?displayProperty=fullName>-Methode.</span><span class="sxs-lookup"><span data-stu-id="842c9-103">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="842c9-104">Durch die **Unload**-Methode wird die angegebene Anwendungsdomäne ordnungsgemäß geschlossen.</span><span class="sxs-lookup"><span data-stu-id="842c9-104">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="842c9-105">Während des Entladevorgangs können keine neuen Threads auf die Anwendungsdomäne zugreifen. Alle anwendungsdomänenspezifischen Strukturen werden freigegeben.</span><span class="sxs-lookup"><span data-stu-id="842c9-105">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="842c9-106">In die Anwendungsdomäne geladene Assemblys werden entfernt und sind nicht weiter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="842c9-106">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="842c9-107">Wenn eine in der Anwendungsdomäne enthaltene Assembly domänenneutral ist, verbleiben deren Daten im Speicher, bis der gesamte Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="842c9-107">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="842c9-108">Das Beenden des gesamten Prozesses ist die einzige Möglichkeit, eine domänenneutrale Assembly zu entladen.</span><span class="sxs-lookup"><span data-stu-id="842c9-108">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="842c9-109">Mitunter kann es vorkommen, dass das Entladen einer Anwendungsdomäne nicht erfolgreich ist und zu einer <xref:System.CannotUnloadAppDomainException> führt.</span><span class="sxs-lookup"><span data-stu-id="842c9-109">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="842c9-110">Im folgenden Codebeispiel wird eine neue Anwendungsdomäne mit dem Namen `MyDomain` erstellt, und es werden einige Informationen auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="842c9-110">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="842c9-111">Anschließend wird die Anwendungsdomäne entladen. Beachten Sie, dass danach der Versuch gestartet wird, den angezeigten Namen der entladenen Anwendungsdomäne auf der Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="842c9-111">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="842c9-112">Dadurch wird eine Ausnahme generiert, die von den „try/catch“-Anweisungen am Ende des Programms abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="842c9-112">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842c9-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="842c9-113">Example</span></span>  
 <span data-ttu-id="842c9-114">[!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)] [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)] [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="842c9-114">[!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)] [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)] [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842c9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="842c9-115">See Also</span></span>  
 <span data-ttu-id="842c9-116">[Programmieren mit Anwendungsdomänen](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="842c9-116">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 <span data-ttu-id="842c9-117">[Gewusst wie: Erstellen einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-create-an-application-domain.md) </span><span class="sxs-lookup"><span data-stu-id="842c9-117">[How to: Create an Application Domain](../../../docs/framework/app-domains/how-to-create-an-application-domain.md) </span></span>  
 [<span data-ttu-id="842c9-118">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="842c9-118">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

