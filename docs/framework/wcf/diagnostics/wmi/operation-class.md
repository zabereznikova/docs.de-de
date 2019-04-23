---
title: Operation-Klasse
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973199"
---
# <a name="operation-class"></a><span data-ttu-id="65f7a-102">Operation-Klasse</span><span class="sxs-lookup"><span data-stu-id="65f7a-102">Operation class</span></span>
<span data-ttu-id="65f7a-103">Vorgang</span><span class="sxs-lookup"><span data-stu-id="65f7a-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f7a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65f7a-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="65f7a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="65f7a-105">Methods</span></span>  
 <span data-ttu-id="65f7a-106">Die Operation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="65f7a-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="65f7a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="65f7a-107">Properties</span></span>  
 <span data-ttu-id="65f7a-108">Die Operation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="65f7a-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="65f7a-109">Aktion</span><span class="sxs-lookup"><span data-stu-id="65f7a-109">Action</span></span>  
 <span data-ttu-id="65f7a-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="65f7a-110">Data type: string</span></span>  
  
 <span data-ttu-id="65f7a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-112">Die WS-Adressierungsaktion der Anforderungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="65f7a-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="65f7a-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="65f7a-113">AsyncPattern</span></span>  
 <span data-ttu-id="65f7a-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="65f7a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="65f7a-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-116">Gibt an, dass ein Vorgang asynchron implementiert wird eine `Begin`[spitze Klammern öffnen/schließen] und `End`[Winkelklammern öffnen/schließen]-Methodenpaar in einem Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="65f7a-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="65f7a-117">Verhalten</span><span class="sxs-lookup"><span data-stu-id="65f7a-117">Behaviors</span></span>  
 <span data-ttu-id="65f7a-118">Datentyp: Behavior-array</span><span class="sxs-lookup"><span data-stu-id="65f7a-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="65f7a-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-120">Die mit diesem Vorgang verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="65f7a-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="65f7a-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="65f7a-121">IsCallback</span></span>  
 <span data-ttu-id="65f7a-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="65f7a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="65f7a-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-124">True, wenn der Vorgang ein Rückrufvorgang ist.</span><span class="sxs-lookup"><span data-stu-id="65f7a-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="65f7a-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="65f7a-125">IsInitiating</span></span>  
 <span data-ttu-id="65f7a-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="65f7a-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="65f7a-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-128">Gibt an, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="65f7a-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="65f7a-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="65f7a-129">IsOneWay</span></span>  
 <span data-ttu-id="65f7a-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="65f7a-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="65f7a-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-132">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="65f7a-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="65f7a-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="65f7a-133">IsTerminating</span></span>  
 <span data-ttu-id="65f7a-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="65f7a-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="65f7a-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-136">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="65f7a-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="65f7a-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="65f7a-137">MethodSignature</span></span>  
 <span data-ttu-id="65f7a-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="65f7a-138">Data type: string</span></span>  
  
 <span data-ttu-id="65f7a-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-140">Die Methodensignatur des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="65f7a-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="65f7a-141">Name</span><span class="sxs-lookup"><span data-stu-id="65f7a-141">Name</span></span>  
 <span data-ttu-id="65f7a-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="65f7a-142">Data type: string</span></span>  
  
 <span data-ttu-id="65f7a-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-144">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="65f7a-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="65f7a-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="65f7a-145">ParameterTypes</span></span>  
 <span data-ttu-id="65f7a-146">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="65f7a-146">Data type: string array</span></span>  
  
 <span data-ttu-id="65f7a-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-148">Die Parametertypen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="65f7a-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="65f7a-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="65f7a-149">ReplyAction</span></span>  
 <span data-ttu-id="65f7a-150">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="65f7a-150">Data type: string</span></span>  
  
 <span data-ttu-id="65f7a-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-152">Der Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="65f7a-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="65f7a-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="65f7a-153">ReturnType</span></span>  
 <span data-ttu-id="65f7a-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="65f7a-154">Data type: string</span></span>  
  
 <span data-ttu-id="65f7a-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="65f7a-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65f7a-156">Der Rückgabetyp des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="65f7a-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65f7a-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65f7a-157">Requirements</span></span>  
  
|<span data-ttu-id="65f7a-158">MOF</span><span class="sxs-lookup"><span data-stu-id="65f7a-158">MOF</span></span>|<span data-ttu-id="65f7a-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="65f7a-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="65f7a-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="65f7a-160">Namespace</span></span>|<span data-ttu-id="65f7a-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="65f7a-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65f7a-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65f7a-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
