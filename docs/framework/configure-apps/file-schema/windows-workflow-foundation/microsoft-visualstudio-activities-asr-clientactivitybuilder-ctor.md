---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c50d9754b71386e6809d46cd9666987a704fbf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="2f422-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="2f422-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="2f422-103">Erstellt eine Instanz der [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) Klasse.</span><span class="sxs-lookup"><span data-stu-id="2f422-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f422-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f422-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f422-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f422-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="2f422-106">Parameterwerte</span><span class="sxs-lookup"><span data-stu-id="2f422-106">Parameter Values</span></span>  
 <span data-ttu-id="2f422-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="2f422-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="2f422-108">beschreibt den Vorgang, der in der zu generierenden Workflowaktivität ausgeführt werden soll, einschließlich des Vorgangsnamens, Rückgabetyps und Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="2f422-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="2f422-109">Der Wert dieses Parameters muss **null**.</span><span class="sxs-lookup"><span data-stu-id="2f422-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="2f422-110">Er sollte einen synchronen Vorgang beschreiben, der einen Nachrichtenvertrag und ein Argument mit einer Nachricht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f422-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="2f422-111">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="2f422-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="2f422-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="2f422-112">*configurationName*</span></span>  
  
 <span data-ttu-id="2f422-113">gibt den zu verwendenden Endpunkt-Konfigurationsnamen an.</span><span class="sxs-lookup"><span data-stu-id="2f422-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="2f422-114">Der Wert dieses Parameters muss entweder **null** oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="2f422-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="2f422-115">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="2f422-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="2f422-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="2f422-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="2f422-117">gibt den Servicenamespace für den Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="2f422-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="2f422-118">Der Wert dieses Parameters muss entweder **null** oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="2f422-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="2f422-119">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="2f422-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f422-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f422-120">See Also</span></span>  
 [<span data-ttu-id="2f422-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="2f422-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
