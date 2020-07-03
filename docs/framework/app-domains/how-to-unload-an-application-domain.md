---
title: 'Vorgehensweise: Entladen einer Anwendungsdomäne'
description: Lesen Sie, wie Sie eine Anwendungsdomäne in .NET entladen, indem Sie die Methode „AppDomain.Unload“ verwenden, um die angegebene Anwendungsdomäne ordnungsgemäß herunterzufahren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
ms.openlocfilehash: b64a9553f63aa4a8deb57f23a97fa464edd64fee
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104653"
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="ed02f-103">Vorgehensweise: Entladen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="ed02f-103">How to: Unload an Application Domain</span></span>
<span data-ttu-id="ed02f-104">Wenn Sie die Nutzung einer Anwendungsdomäne beenden möchten, entladen Sie sie mithilfe der <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="ed02f-104">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ed02f-105">Durch die **Unload**-Methode wird die angegebene Anwendungsdomäne ordnungsgemäß geschlossen.</span><span class="sxs-lookup"><span data-stu-id="ed02f-105">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="ed02f-106">Während des Entladevorgangs können keine neuen Threads auf die Anwendungsdomäne zugreifen. Alle anwendungsdomänenspezifischen Strukturen werden freigegeben.</span><span class="sxs-lookup"><span data-stu-id="ed02f-106">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="ed02f-107">In die Anwendungsdomäne geladene Assemblys werden entfernt und sind nicht weiter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed02f-107">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="ed02f-108">Wenn eine in der Anwendungsdomäne enthaltene Assembly domänenneutral ist, verbleiben deren Daten im Speicher, bis der gesamte Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed02f-108">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="ed02f-109">Das Beenden des gesamten Prozesses ist die einzige Möglichkeit, eine domänenneutrale Assembly zu entladen.</span><span class="sxs-lookup"><span data-stu-id="ed02f-109">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="ed02f-110">Mitunter kann es vorkommen, dass das Entladen einer Anwendungsdomäne nicht erfolgreich ist und zu einer <xref:System.CannotUnloadAppDomainException> führt.</span><span class="sxs-lookup"><span data-stu-id="ed02f-110">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="ed02f-111">Im folgenden Codebeispiel wird eine neue Anwendungsdomäne mit dem Namen `MyDomain` erstellt, und es werden einige Informationen auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed02f-111">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="ed02f-112">Anschließend wird die Anwendungsdomäne entladen. Beachten Sie, dass danach der Versuch gestartet wird, den angezeigten Namen der entladenen Anwendungsdomäne auf der Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ed02f-112">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="ed02f-113">Dadurch wird eine Ausnahme generiert, die von den „try/catch“-Anweisungen am Ende des Programms abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="ed02f-113">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed02f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed02f-114">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ed02f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed02f-115">See also</span></span>

- [<span data-ttu-id="ed02f-116">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="ed02f-116">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="ed02f-117">How to: Erstellen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="ed02f-117">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)
- [<span data-ttu-id="ed02f-118">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="ed02f-118">Using Application Domains</span></span>](use.md)
