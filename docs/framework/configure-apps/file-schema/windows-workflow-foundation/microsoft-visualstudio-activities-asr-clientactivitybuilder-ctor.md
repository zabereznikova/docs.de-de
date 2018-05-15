---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: aca5a6ad07d96e08203e9e1cad7dec632035caf0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="748dc-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="748dc-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="748dc-103">Erstellt eine Instanz der [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) Klasse.</span><span class="sxs-lookup"><span data-stu-id="748dc-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="748dc-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="748dc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="748dc-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="748dc-106">Parameterwerte</span><span class="sxs-lookup"><span data-stu-id="748dc-106">Parameter Values</span></span>  
 <span data-ttu-id="748dc-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="748dc-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="748dc-108">beschreibt den Vorgang, der in der zu generierenden Workflowaktivität ausgeführt werden soll, einschließlich des Vorgangsnamens, Rückgabetyps und Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="748dc-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="748dc-109">Der Wert dieses Parameters muss **null**.</span><span class="sxs-lookup"><span data-stu-id="748dc-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="748dc-110">Er sollte einen synchronen Vorgang beschreiben, der einen Nachrichtenvertrag und ein Argument mit einer Nachricht verwendet.</span><span class="sxs-lookup"><span data-stu-id="748dc-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="748dc-111">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="748dc-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="748dc-112">*ConfigurationName*</span><span class="sxs-lookup"><span data-stu-id="748dc-112">*configurationName*</span></span>  
  
 <span data-ttu-id="748dc-113">gibt den zu verwendenden Endpunkt-Konfigurationsnamen an.</span><span class="sxs-lookup"><span data-stu-id="748dc-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="748dc-114">Der Wert dieses Parameters muss entweder **null** oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="748dc-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="748dc-115">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="748dc-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="748dc-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="748dc-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="748dc-117">gibt den Servicenamespace für den Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="748dc-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="748dc-118">Der Wert dieses Parameters muss entweder **null** oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="748dc-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="748dc-119">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="748dc-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="748dc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="748dc-120">See Also</span></span>  
 [<span data-ttu-id="748dc-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="748dc-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
