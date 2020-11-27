---
title: Operation-Klasse
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 6b47d933dc84813532398830c92c95210208a709
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269157"
---
# <a name="operation-class"></a><span data-ttu-id="24246-102">Operation-Klasse</span><span class="sxs-lookup"><span data-stu-id="24246-102">Operation class</span></span>

<span data-ttu-id="24246-103">Vorgang</span><span class="sxs-lookup"><span data-stu-id="24246-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24246-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24246-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="24246-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="24246-105">Methods</span></span>  

 <span data-ttu-id="24246-106">Die Operation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="24246-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="24246-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="24246-107">Properties</span></span>  

 <span data-ttu-id="24246-108">Die Operation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="24246-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="24246-109">Action</span><span class="sxs-lookup"><span data-stu-id="24246-109">Action</span></span>  

 <span data-ttu-id="24246-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="24246-110">Data type: string</span></span>  
  
 <span data-ttu-id="24246-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-112">Die WS-Adressierungsaktion der Anforderungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="24246-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="24246-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="24246-113">AsyncPattern</span></span>  

 <span data-ttu-id="24246-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="24246-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="24246-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-116">Gibt an, dass ein Vorgang asynchron mithilfe `Begin` der Methoden Paare [öffnende/schließende spitzen Klammern] und `End` [öffnende/schließende spitze Klammern] in einem Dienstvertrag implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="24246-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="24246-117">Verhalten</span><span class="sxs-lookup"><span data-stu-id="24246-117">Behaviors</span></span>  

 <span data-ttu-id="24246-118">Datentyp: Behavior-Array</span><span class="sxs-lookup"><span data-stu-id="24246-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="24246-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-120">Die mit diesem Vorgang verknüpften Verhalten.</span><span class="sxs-lookup"><span data-stu-id="24246-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="24246-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="24246-121">IsCallback</span></span>  

 <span data-ttu-id="24246-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="24246-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="24246-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-124">True, wenn der Vorgang ein Rückrufvorgang ist.</span><span class="sxs-lookup"><span data-stu-id="24246-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="24246-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="24246-125">IsInitiating</span></span>  

 <span data-ttu-id="24246-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="24246-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="24246-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-128">Gibt an, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann.</span><span class="sxs-lookup"><span data-stu-id="24246-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="24246-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="24246-129">IsOneWay</span></span>  

 <span data-ttu-id="24246-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="24246-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="24246-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-132">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="24246-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="24246-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="24246-133">IsTerminating</span></span>  

 <span data-ttu-id="24246-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="24246-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="24246-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-136">Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="24246-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="24246-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="24246-137">MethodSignature</span></span>  

 <span data-ttu-id="24246-138">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="24246-138">Data type: string</span></span>  
  
 <span data-ttu-id="24246-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-140">Die Methodensignatur des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="24246-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="24246-141">Name</span><span class="sxs-lookup"><span data-stu-id="24246-141">Name</span></span>  

 <span data-ttu-id="24246-142">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="24246-142">Data type: string</span></span>  
  
 <span data-ttu-id="24246-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-144">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="24246-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="24246-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="24246-145">ParameterTypes</span></span>  

 <span data-ttu-id="24246-146">Datentyp: Zeichenfolgenarray</span><span class="sxs-lookup"><span data-stu-id="24246-146">Data type: string array</span></span>  
  
 <span data-ttu-id="24246-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-148">Die Parametertypen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="24246-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="24246-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="24246-149">ReplyAction</span></span>  

 <span data-ttu-id="24246-150">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="24246-150">Data type: string</span></span>  
  
 <span data-ttu-id="24246-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-152">Der Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="24246-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="24246-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="24246-153">ReturnType</span></span>  

 <span data-ttu-id="24246-154">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="24246-154">Data type: string</span></span>  
  
 <span data-ttu-id="24246-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="24246-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24246-156">Der Rückgabetyp des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="24246-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24246-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24246-157">Requirements</span></span>  
  
|<span data-ttu-id="24246-158">MOF</span><span class="sxs-lookup"><span data-stu-id="24246-158">MOF</span></span>|<span data-ttu-id="24246-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="24246-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="24246-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="24246-160">Namespace</span></span>|<span data-ttu-id="24246-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="24246-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24246-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24246-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
