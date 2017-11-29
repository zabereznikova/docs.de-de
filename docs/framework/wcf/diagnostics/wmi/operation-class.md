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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 739f8309e7a01eeecf921b50fcde24417fbbc515
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="operation-class"></a><span data-ttu-id="e2a67-102">Operation-Klasse</span><span class="sxs-lookup"><span data-stu-id="e2a67-102">Operation class</span></span>
<span data-ttu-id="e2a67-103">Vorgang</span><span class="sxs-lookup"><span data-stu-id="e2a67-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2a67-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e2a67-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e2a67-105">Methods</span></span>  
 <span data-ttu-id="e2a67-106">Die Operation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e2a67-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e2a67-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e2a67-107">Properties</span></span>  
 <span data-ttu-id="e2a67-108">Die Operation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e2a67-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="e2a67-109">Aktion</span><span class="sxs-lookup"><span data-stu-id="e2a67-109">Action</span></span>  
 <span data-ttu-id="e2a67-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2a67-110">Data type: string</span></span>  
  
 <span data-ttu-id="e2a67-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-112">Die WS-Adressierungsaktion der Anforderungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="e2a67-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="e2a67-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="e2a67-113">AsyncPattern</span></span>  
 <span data-ttu-id="e2a67-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e2a67-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2a67-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-116">Gibt an, dass ein Vorgang implementiert wird asynchron mit einem `Begin`[spitze Klammern öffnen/schließen] und `End`[Klammern öffnen/schließen]-Methodenpaar in einem Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="e2a67-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="e2a67-117">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e2a67-117">Behaviors</span></span>  
 <span data-ttu-id="e2a67-118">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="e2a67-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="e2a67-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-120">Die mit diesem Vorgang verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e2a67-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="e2a67-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="e2a67-121">IsCallback</span></span>  
 <span data-ttu-id="e2a67-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e2a67-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2a67-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-124">True, wenn der Vorgang ein Rückrufvorgang ist.</span><span class="sxs-lookup"><span data-stu-id="e2a67-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="e2a67-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="e2a67-125">IsInitiating</span></span>  
 <span data-ttu-id="e2a67-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e2a67-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2a67-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-128">Gibt an, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="e2a67-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="e2a67-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="e2a67-129">IsOneWay</span></span>  
 <span data-ttu-id="e2a67-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e2a67-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2a67-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-132">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e2a67-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="e2a67-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="e2a67-133">IsTerminating</span></span>  
 <span data-ttu-id="e2a67-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e2a67-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="e2a67-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-136">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e2a67-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="e2a67-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="e2a67-137">MethodSignature</span></span>  
 <span data-ttu-id="e2a67-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2a67-138">Data type: string</span></span>  
  
 <span data-ttu-id="e2a67-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-140">Die Methodensignatur des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e2a67-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e2a67-141">Name</span><span class="sxs-lookup"><span data-stu-id="e2a67-141">Name</span></span>  
 <span data-ttu-id="e2a67-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2a67-142">Data type: string</span></span>  
  
 <span data-ttu-id="e2a67-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-144">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e2a67-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="e2a67-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="e2a67-145">ParameterTypes</span></span>  
 <span data-ttu-id="e2a67-146">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="e2a67-146">Data type: string array</span></span>  
  
 <span data-ttu-id="e2a67-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-148">Die Parametertypen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e2a67-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="e2a67-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="e2a67-149">ReplyAction</span></span>  
 <span data-ttu-id="e2a67-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2a67-150">Data type: string</span></span>  
  
 <span data-ttu-id="e2a67-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-152">Der Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e2a67-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="e2a67-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="e2a67-153">ReturnType</span></span>  
 <span data-ttu-id="e2a67-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e2a67-154">Data type: string</span></span>  
  
 <span data-ttu-id="e2a67-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e2a67-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2a67-156">Der Rückgabetyp des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e2a67-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2a67-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2a67-157">Requirements</span></span>  
  
|<span data-ttu-id="e2a67-158">MOF</span><span class="sxs-lookup"><span data-stu-id="e2a67-158">MOF</span></span>|<span data-ttu-id="e2a67-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e2a67-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e2a67-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="e2a67-160">Namespace</span></span>|<span data-ttu-id="e2a67-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2a67-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2a67-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2a67-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
