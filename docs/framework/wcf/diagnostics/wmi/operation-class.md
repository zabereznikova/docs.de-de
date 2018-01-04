---
title: Operation-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54566bc452baa2e02cef7d8d13d29fcd5864c95c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="operation-class"></a><span data-ttu-id="9d170-102">Operation-Klasse</span><span class="sxs-lookup"><span data-stu-id="9d170-102">Operation class</span></span>
<span data-ttu-id="9d170-103">Vorgang</span><span class="sxs-lookup"><span data-stu-id="9d170-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d170-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d170-104">Syntax</span></span>  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9d170-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d170-105">Methods</span></span>  
 <span data-ttu-id="9d170-106">Die Operation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="9d170-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9d170-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9d170-107">Properties</span></span>  
 <span data-ttu-id="9d170-108">Die Operation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9d170-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="9d170-109">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d170-109">Action</span></span>  
 <span data-ttu-id="9d170-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d170-110">Data type: string</span></span>  
  
 <span data-ttu-id="9d170-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-112">Die WS-Adressierungsaktion der Anforderungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="9d170-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="9d170-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="9d170-113">AsyncPattern</span></span>  
 <span data-ttu-id="9d170-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9d170-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9d170-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-116">Gibt an, dass ein Vorgang implementiert wird asynchron mit einem `Begin`[spitze Klammern öffnen/schließen] und `End`[Klammern öffnen/schließen]-Methodenpaar in einem Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="9d170-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="9d170-117">Verhalten</span><span class="sxs-lookup"><span data-stu-id="9d170-117">Behaviors</span></span>  
 <span data-ttu-id="9d170-118">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="9d170-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="9d170-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-120">Die mit diesem Vorgang verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9d170-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="9d170-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="9d170-121">IsCallback</span></span>  
 <span data-ttu-id="9d170-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9d170-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="9d170-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-124">True, wenn der Vorgang ein Rückrufvorgang ist.</span><span class="sxs-lookup"><span data-stu-id="9d170-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="9d170-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="9d170-125">IsInitiating</span></span>  
 <span data-ttu-id="9d170-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9d170-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="9d170-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-128">Gibt an, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="9d170-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="9d170-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="9d170-129">IsOneWay</span></span>  
 <span data-ttu-id="9d170-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9d170-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="9d170-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-132">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9d170-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="9d170-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="9d170-133">IsTerminating</span></span>  
 <span data-ttu-id="9d170-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9d170-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="9d170-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-136">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9d170-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="9d170-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="9d170-137">MethodSignature</span></span>  
 <span data-ttu-id="9d170-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d170-138">Data type: string</span></span>  
  
 <span data-ttu-id="9d170-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-140">Die Methodensignatur des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="9d170-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="9d170-141">name</span><span class="sxs-lookup"><span data-stu-id="9d170-141">Name</span></span>  
 <span data-ttu-id="9d170-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d170-142">Data type: string</span></span>  
  
 <span data-ttu-id="9d170-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-144">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="9d170-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="9d170-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="9d170-145">ParameterTypes</span></span>  
 <span data-ttu-id="9d170-146">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="9d170-146">Data type: string array</span></span>  
  
 <span data-ttu-id="9d170-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-148">Die Parametertypen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="9d170-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="9d170-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="9d170-149">ReplyAction</span></span>  
 <span data-ttu-id="9d170-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d170-150">Data type: string</span></span>  
  
 <span data-ttu-id="9d170-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-152">Der Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="9d170-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="9d170-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="9d170-153">ReturnType</span></span>  
 <span data-ttu-id="9d170-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9d170-154">Data type: string</span></span>  
  
 <span data-ttu-id="9d170-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d170-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d170-156">Der Rückgabetyp des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="9d170-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d170-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d170-157">Requirements</span></span>  
  
|<span data-ttu-id="9d170-158">MOF</span><span class="sxs-lookup"><span data-stu-id="9d170-158">MOF</span></span>|<span data-ttu-id="9d170-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9d170-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9d170-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="9d170-160">Namespace</span></span>|<span data-ttu-id="9d170-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d170-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d170-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d170-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
