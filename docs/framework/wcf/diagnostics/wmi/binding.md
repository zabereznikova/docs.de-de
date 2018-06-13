---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 0260b75a0f49e0f6f72d7d1eda642d0a494d2892
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487006"
---
# <a name="binding"></a><span data-ttu-id="6c62e-102">Bindung</span><span class="sxs-lookup"><span data-stu-id="6c62e-102">Binding</span></span>
<span data-ttu-id="6c62e-103">wmi-Bindung</span><span class="sxs-lookup"><span data-stu-id="6c62e-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c62e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c62e-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="6c62e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6c62e-105">Methods</span></span>  
 <span data-ttu-id="6c62e-106">Die Bindungsklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="6c62e-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6c62e-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6c62e-107">Properties</span></span>  
 <span data-ttu-id="6c62e-108">Die Bindungsklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6c62e-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="6c62e-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="6c62e-109">BindingElements</span></span>  
 <span data-ttu-id="6c62e-110">Datentyp: BindingElement-Array</span><span class="sxs-lookup"><span data-stu-id="6c62e-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="6c62e-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-112">Die Auflistung der durch die Bindung implementierten Bindungselemente.</span><span class="sxs-lookup"><span data-stu-id="6c62e-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="6c62e-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="6c62e-113">CloseTimeout</span></span>  
 <span data-ttu-id="6c62e-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="6c62e-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="6c62e-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-116">Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6c62e-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="6c62e-117">name</span><span class="sxs-lookup"><span data-stu-id="6c62e-117">Name</span></span>  
 <span data-ttu-id="6c62e-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="6c62e-118">Data type: string</span></span>  
  
 <span data-ttu-id="6c62e-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-120">Der Name der Bindung.</span><span class="sxs-lookup"><span data-stu-id="6c62e-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="6c62e-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="6c62e-121">Namespace</span></span>  
 <span data-ttu-id="6c62e-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="6c62e-122">Data type: string</span></span>  
  
 <span data-ttu-id="6c62e-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-124">Der XML-Namespace der Bindung.</span><span class="sxs-lookup"><span data-stu-id="6c62e-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="6c62e-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="6c62e-125">OpenTimeout</span></span>  
 <span data-ttu-id="6c62e-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="6c62e-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="6c62e-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-128">Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6c62e-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="6c62e-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="6c62e-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="6c62e-130">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="6c62e-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="6c62e-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-132">Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6c62e-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="6c62e-133">Schema</span><span class="sxs-lookup"><span data-stu-id="6c62e-133">Scheme</span></span>  
 <span data-ttu-id="6c62e-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="6c62e-134">Data type: string</span></span>  
  
 <span data-ttu-id="6c62e-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-136">Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c62e-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="6c62e-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="6c62e-137">SendTimeout</span></span>  
 <span data-ttu-id="6c62e-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="6c62e-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="6c62e-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6c62e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c62e-140">Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6c62e-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c62e-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c62e-141">Requirements</span></span>  
  
|<span data-ttu-id="6c62e-142">MOF</span><span class="sxs-lookup"><span data-stu-id="6c62e-142">MOF</span></span>|<span data-ttu-id="6c62e-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6c62e-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6c62e-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="6c62e-144">Namespace</span></span>|<span data-ttu-id="6c62e-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6c62e-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c62e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c62e-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
