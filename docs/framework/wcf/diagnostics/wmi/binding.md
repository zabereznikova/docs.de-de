---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: a040cc6e12833d2c737eb14c591300e5873ddce7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106514"
---
# <a name="binding"></a><span data-ttu-id="7a9dd-102">Bindung</span><span class="sxs-lookup"><span data-stu-id="7a9dd-102">Binding</span></span>
<span data-ttu-id="7a9dd-103">wmi-Bindung</span><span class="sxs-lookup"><span data-stu-id="7a9dd-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a9dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a9dd-104">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7a9dd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7a9dd-105">Methods</span></span>  
 <span data-ttu-id="7a9dd-106">Die Bindungsklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7a9dd-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7a9dd-107">Properties</span></span>  
 <span data-ttu-id="7a9dd-108">Die Bindungsklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="7a9dd-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="7a9dd-109">BindingElements</span></span>  
 <span data-ttu-id="7a9dd-110">Datentyp: BindingElement-array</span><span class="sxs-lookup"><span data-stu-id="7a9dd-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="7a9dd-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-112">Die Auflistung der durch die Bindung implementierten Bindungselemente.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="7a9dd-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="7a9dd-113">CloseTimeout</span></span>  
 <span data-ttu-id="7a9dd-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a9dd-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-116">Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="7a9dd-117">Name</span><span class="sxs-lookup"><span data-stu-id="7a9dd-117">Name</span></span>  
 <span data-ttu-id="7a9dd-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-118">Data type: string</span></span>  
  
 <span data-ttu-id="7a9dd-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-120">Der Name der Bindung.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="7a9dd-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="7a9dd-121">Namespace</span></span>  
 <span data-ttu-id="7a9dd-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-122">Data type: string</span></span>  
  
 <span data-ttu-id="7a9dd-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-124">Der XML-Namespace der Bindung.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="7a9dd-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="7a9dd-125">OpenTimeout</span></span>  
 <span data-ttu-id="7a9dd-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a9dd-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-128">Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="7a9dd-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="7a9dd-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="7a9dd-130">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a9dd-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-132">Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="7a9dd-133">Schema</span><span class="sxs-lookup"><span data-stu-id="7a9dd-133">Scheme</span></span>  
 <span data-ttu-id="7a9dd-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-134">Data type: string</span></span>  
  
 <span data-ttu-id="7a9dd-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-136">Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="7a9dd-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="7a9dd-137">SendTimeout</span></span>  
 <span data-ttu-id="7a9dd-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="7a9dd-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a9dd-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7a9dd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a9dd-140">Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a9dd-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a9dd-141">Requirements</span></span>  
  
|<span data-ttu-id="7a9dd-142">MOF</span><span class="sxs-lookup"><span data-stu-id="7a9dd-142">MOF</span></span>|<span data-ttu-id="7a9dd-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7a9dd-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7a9dd-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="7a9dd-144">Namespace</span></span>|<span data-ttu-id="7a9dd-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7a9dd-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a9dd-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a9dd-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
