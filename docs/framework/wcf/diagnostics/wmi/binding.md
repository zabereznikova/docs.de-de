---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6553d1e1c030a30eed74ff81d3e07e28a9f25b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="binding"></a><span data-ttu-id="39c40-102">Bindung</span><span class="sxs-lookup"><span data-stu-id="39c40-102">Binding</span></span>
<span data-ttu-id="39c40-103">wmi-Bindung</span><span class="sxs-lookup"><span data-stu-id="39c40-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39c40-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="39c40-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="39c40-105">Methods</span></span>  
 <span data-ttu-id="39c40-106">Die Bindungsklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="39c40-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="39c40-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="39c40-107">Properties</span></span>  
 <span data-ttu-id="39c40-108">Die Bindungsklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="39c40-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="39c40-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="39c40-109">BindingElements</span></span>  
 <span data-ttu-id="39c40-110">Datentyp: BindingElement-Array</span><span class="sxs-lookup"><span data-stu-id="39c40-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="39c40-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-112">Die Auflistung der durch die Bindung implementierten Bindungselemente.</span><span class="sxs-lookup"><span data-stu-id="39c40-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="39c40-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="39c40-113">CloseTimeout</span></span>  
 <span data-ttu-id="39c40-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="39c40-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="39c40-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-116">Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="39c40-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="39c40-117">name</span><span class="sxs-lookup"><span data-stu-id="39c40-117">Name</span></span>  
 <span data-ttu-id="39c40-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="39c40-118">Data type: string</span></span>  
  
 <span data-ttu-id="39c40-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-120">Der Name der Bindung.</span><span class="sxs-lookup"><span data-stu-id="39c40-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="39c40-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="39c40-121">Namespace</span></span>  
 <span data-ttu-id="39c40-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="39c40-122">Data type: string</span></span>  
  
 <span data-ttu-id="39c40-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-124">Der XML-Namespace der Bindung.</span><span class="sxs-lookup"><span data-stu-id="39c40-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="39c40-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="39c40-125">OpenTimeout</span></span>  
 <span data-ttu-id="39c40-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="39c40-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="39c40-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-128">Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="39c40-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="39c40-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="39c40-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="39c40-130">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="39c40-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="39c40-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-132">Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="39c40-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="39c40-133">Schema</span><span class="sxs-lookup"><span data-stu-id="39c40-133">Scheme</span></span>  
 <span data-ttu-id="39c40-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="39c40-134">Data type: string</span></span>  
  
 <span data-ttu-id="39c40-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-136">Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="39c40-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="39c40-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="39c40-137">SendTimeout</span></span>  
 <span data-ttu-id="39c40-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="39c40-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="39c40-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="39c40-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39c40-140">Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="39c40-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c40-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39c40-141">Requirements</span></span>  
  
|<span data-ttu-id="39c40-142">MOF</span><span class="sxs-lookup"><span data-stu-id="39c40-142">MOF</span></span>|<span data-ttu-id="39c40-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="39c40-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="39c40-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="39c40-144">Namespace</span></span>|<span data-ttu-id="39c40-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="39c40-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39c40-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39c40-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
