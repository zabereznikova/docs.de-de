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
ms.openlocfilehash: 4e7595efd3037a525d272dbcd60243db29f2efa6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150829"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="26258-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="26258-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>

<span data-ttu-id="26258-103">Erstellt eine Instanz der [Microsoft. VisualStudio. Activities. ASR. clientactivitybuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="26258-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26258-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26258-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26258-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="26258-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="26258-106">Parameterwerte</span><span class="sxs-lookup"><span data-stu-id="26258-106">Parameter Values</span></span>  

 <span data-ttu-id="26258-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="26258-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="26258-108">beschreibt den Vorgang, der in der zu generierenden Workflowaktivität ausgeführt werden soll, einschließlich des Vorgangsnamens, Rückgabetyps und Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="26258-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="26258-109">Der Wert dieses Parameters darf nicht **null**sein.</span><span class="sxs-lookup"><span data-stu-id="26258-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="26258-110">Er sollte einen synchronen Vorgang beschreiben, der einen Nachrichtenvertrag und ein Argument mit einer Nachricht verwendet.</span><span class="sxs-lookup"><span data-stu-id="26258-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="26258-111">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="26258-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="26258-112">*ConfigurationName*</span><span class="sxs-lookup"><span data-stu-id="26258-112">*configurationName*</span></span>  
  
 <span data-ttu-id="26258-113">gibt den zu verwendenden Endpunkt-Konfigurationsnamen an.</span><span class="sxs-lookup"><span data-stu-id="26258-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="26258-114">Der Wert dieses Parameters darf nicht **null** oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="26258-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="26258-115">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="26258-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="26258-116">*proxynamespace*</span><span class="sxs-lookup"><span data-stu-id="26258-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="26258-117">gibt den Servicenamespace für den Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="26258-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="26258-118">Der Wert dieses Parameters darf nicht **null** oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="26258-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="26258-119">Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="26258-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26258-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26258-120">See also</span></span>

- [<span data-ttu-id="26258-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="26258-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
