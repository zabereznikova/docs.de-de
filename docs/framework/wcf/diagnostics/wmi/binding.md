---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: aaf0dd9d6918f2c248942cee3773eee8332adda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552839"
---
# <a name="binding"></a><span data-ttu-id="0c369-102">Bindung</span><span class="sxs-lookup"><span data-stu-id="0c369-102">Binding</span></span>
<span data-ttu-id="0c369-103">wmi-Bindung</span><span class="sxs-lookup"><span data-stu-id="0c369-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c369-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c369-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0c369-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0c369-105">Methods</span></span>  
 <span data-ttu-id="0c369-106">Die Bindungsklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="0c369-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0c369-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0c369-107">Properties</span></span>  
 <span data-ttu-id="0c369-108">Die Bindungsklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0c369-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="0c369-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="0c369-109">BindingElements</span></span>  
 <span data-ttu-id="0c369-110">Datentyp: BindingElement-array</span><span class="sxs-lookup"><span data-stu-id="0c369-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="0c369-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-112">Die Auflistung der durch die Bindung implementierten Bindungselemente.</span><span class="sxs-lookup"><span data-stu-id="0c369-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="0c369-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="0c369-113">CloseTimeout</span></span>  
 <span data-ttu-id="0c369-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0c369-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="0c369-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-116">Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0c369-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="0c369-117">name</span><span class="sxs-lookup"><span data-stu-id="0c369-117">Name</span></span>  
 <span data-ttu-id="0c369-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0c369-118">Data type: string</span></span>  
  
 <span data-ttu-id="0c369-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-120">Der Name der Bindung.</span><span class="sxs-lookup"><span data-stu-id="0c369-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="0c369-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="0c369-121">Namespace</span></span>  
 <span data-ttu-id="0c369-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0c369-122">Data type: string</span></span>  
  
 <span data-ttu-id="0c369-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-124">Der XML-Namespace der Bindung.</span><span class="sxs-lookup"><span data-stu-id="0c369-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="0c369-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="0c369-125">OpenTimeout</span></span>  
 <span data-ttu-id="0c369-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0c369-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="0c369-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-128">Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0c369-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="0c369-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="0c369-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="0c369-130">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0c369-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="0c369-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-132">Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0c369-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="0c369-133">Schema</span><span class="sxs-lookup"><span data-stu-id="0c369-133">Scheme</span></span>  
 <span data-ttu-id="0c369-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0c369-134">Data type: string</span></span>  
  
 <span data-ttu-id="0c369-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-136">Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c369-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="0c369-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="0c369-137">SendTimeout</span></span>  
 <span data-ttu-id="0c369-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0c369-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="0c369-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0c369-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0c369-140">Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0c369-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c369-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c369-141">Requirements</span></span>  
  
|<span data-ttu-id="0c369-142">MOF</span><span class="sxs-lookup"><span data-stu-id="0c369-142">MOF</span></span>|<span data-ttu-id="0c369-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0c369-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0c369-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="0c369-144">Namespace</span></span>|<span data-ttu-id="0c369-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0c369-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c369-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c369-146">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
