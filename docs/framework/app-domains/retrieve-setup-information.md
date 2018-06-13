---
title: Abrufen von Setupinformationen aus einer Anwendungsdomäne
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fab54080a529a9b5a93c06a4f249a9c14ecd7af
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743887"
---
# <a name="retrieving-setup-information-from-an-application-domain"></a><span data-ttu-id="240e2-102">Abrufen von Setupinformationen aus einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="240e2-102">Retrieving Setup Information from an Application Domain</span></span>
<span data-ttu-id="240e2-103">Jede Instanz einer Anwendungsdomäne besteht sowohl aus Eigenschaften als auch aus <xref:System.AppDomainSetup>-Informationen.</span><span class="sxs-lookup"><span data-stu-id="240e2-103">Each instance of an application domain consists of both properties and <xref:System.AppDomainSetup> information.</span></span> <span data-ttu-id="240e2-104">Sie können Setupinformationen aus einer Anwendungsdomäne mit der Klasse <xref:System.AppDomain?displayProperty=nameWithType> abrufen.</span><span class="sxs-lookup"><span data-stu-id="240e2-104">You can retrieve setup information from an application domain using the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="240e2-105">Diese Klasse stellt mehrere Member zur Verfügung, die Konfigurierungsinformationen zu Anwendungsdomänen abrufen.</span><span class="sxs-lookup"><span data-stu-id="240e2-105">This class provides several members that retrieve configuration information about an application domain.</span></span>  
  
 <span data-ttu-id="240e2-106">Sie können das Objekt **AppDomainSetup** für die Anwendungsdomäne abfragen, um Setupinformationen zu erhalten, die der Erstellung an die Domäne übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="240e2-106">You can also query the **AppDomainSetup** object for the application domain to obtain setup information that was passed to the domain when it was created.</span></span>  
  
 <span data-ttu-id="240e2-107">Im folgenden Beispiel wird eine neue Anwendungsdomäne erstellt, und anschließend werden mehrere Memberwerte an die Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="240e2-107">The following example creates a new application domain and then prints several member values to the console.</span></span>  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 <span data-ttu-id="240e2-108">In folgendem Beispielen werden Setupinformationen für die Anwendungsdomäne festgelegt und anschließend abgerufen.</span><span class="sxs-lookup"><span data-stu-id="240e2-108">The following example sets, and then retrieves, setup information for an application domain.</span></span> <span data-ttu-id="240e2-109">Beachten Sie, dass `AppDomain.SetupInformation.ApplicationBase` die Konfigurationsinformationen abruft.</span><span class="sxs-lookup"><span data-stu-id="240e2-109">Note that `AppDomain.SetupInformation.ApplicationBase` gets the configuration information.</span></span>  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="240e2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="240e2-110">See Also</span></span>  
 [<span data-ttu-id="240e2-111">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="240e2-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)  
 [<span data-ttu-id="240e2-112">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="240e2-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
