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
ms.openlocfilehash: b9e44d161e1229db9145f4ed7e337396bbd98c68
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="binding"></a><span data-ttu-id="17e54-102">Bindung</span><span class="sxs-lookup"><span data-stu-id="17e54-102">Binding</span></span>
<span data-ttu-id="17e54-103">wmi-Bindung</span><span class="sxs-lookup"><span data-stu-id="17e54-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17e54-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="17e54-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="17e54-105">Methods</span></span>  
 <span data-ttu-id="17e54-106">Die Bindungsklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="17e54-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="17e54-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="17e54-107">Properties</span></span>  
 <span data-ttu-id="17e54-108">Die Bindungsklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="17e54-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="17e54-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="17e54-109">BindingElements</span></span>  
 <span data-ttu-id="17e54-110">Datentyp: BindingElement-Array</span><span class="sxs-lookup"><span data-stu-id="17e54-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="17e54-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-112">Die Auflistung der durch die Bindung implementierten Bindungselemente.</span><span class="sxs-lookup"><span data-stu-id="17e54-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="17e54-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="17e54-113">CloseTimeout</span></span>  
 <span data-ttu-id="17e54-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="17e54-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="17e54-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-116">Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17e54-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="17e54-117">Name</span><span class="sxs-lookup"><span data-stu-id="17e54-117">Name</span></span>  
 <span data-ttu-id="17e54-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="17e54-118">Data type: string</span></span>  
  
 <span data-ttu-id="17e54-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-120">Der Name der Bindung.</span><span class="sxs-lookup"><span data-stu-id="17e54-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="17e54-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="17e54-121">Namespace</span></span>  
 <span data-ttu-id="17e54-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="17e54-122">Data type: string</span></span>  
  
 <span data-ttu-id="17e54-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-124">Der XML-Namespace der Bindung.</span><span class="sxs-lookup"><span data-stu-id="17e54-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="17e54-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="17e54-125">OpenTimeout</span></span>  
 <span data-ttu-id="17e54-126">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="17e54-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="17e54-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-128">Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17e54-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="17e54-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="17e54-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="17e54-130">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="17e54-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="17e54-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-132">Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17e54-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="17e54-133">Schema</span><span class="sxs-lookup"><span data-stu-id="17e54-133">Scheme</span></span>  
 <span data-ttu-id="17e54-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="17e54-134">Data type: string</span></span>  
  
 <span data-ttu-id="17e54-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-136">Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="17e54-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="17e54-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="17e54-137">SendTimeout</span></span>  
 <span data-ttu-id="17e54-138">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="17e54-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="17e54-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="17e54-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="17e54-140">Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17e54-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17e54-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17e54-141">Requirements</span></span>  
  
|<span data-ttu-id="17e54-142">MOF</span><span class="sxs-lookup"><span data-stu-id="17e54-142">MOF</span></span>|<span data-ttu-id="17e54-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="17e54-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="17e54-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="17e54-144">Namespace</span></span>|<span data-ttu-id="17e54-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="17e54-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17e54-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17e54-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
