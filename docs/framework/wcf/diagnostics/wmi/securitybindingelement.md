---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 601e3fafd9aa876186b7f78dfdcb87a2336ddfcd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185770"
---
# <a name="securitybindingelement"></a><span data-ttu-id="4c4d1-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4c4d1-102">SecurityBindingElement</span></span>
<span data-ttu-id="4c4d1-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4c4d1-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c4d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c4d1-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4c4d1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4c4d1-105">Methods</span></span>  
 <span data-ttu-id="4c4d1-106">Die SecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4c4d1-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4c4d1-107">Properties</span></span>  
 <span data-ttu-id="4c4d1-108">Die SecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4c4d1-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="4c4d1-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="4c4d1-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="4c4d1-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4c4d1-110">Data type: string</span></span>  
  
 <span data-ttu-id="4c4d1-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4c4d1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c4d1-112">Gibt die Algorithmen an, die mit der Bindung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="4c4d1-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="4c4d1-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="4c4d1-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="4c4d1-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4c4d1-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4c4d1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c4d1-116">Ein boolescher Wert, der angibt, ob jede Nachricht einen Timestamp enthält.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="4c4d1-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="4c4d1-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="4c4d1-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4c4d1-118">Data type: string</span></span>  
  
 <span data-ttu-id="4c4d1-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4c4d1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c4d1-120">Die Entropiequelle zum Erstellen von Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="4c4d1-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4c4d1-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="4c4d1-122">Datentyp: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4c4d1-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="4c4d1-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4c4d1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c4d1-124">Die bindungsspezifischen Sicherheitseigenschaften für den lokalen Dienst.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="4c4d1-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="4c4d1-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="4c4d1-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4c4d1-126">Data type: string</span></span>  
  
 <span data-ttu-id="4c4d1-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4c4d1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c4d1-128">Die für Nachrichtensicherheit verwendete Version.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="4c4d1-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="4c4d1-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="4c4d1-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4c4d1-130">Data type: string</span></span>  
  
 <span data-ttu-id="4c4d1-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4c4d1-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c4d1-132">Die Reihenfolge der Elemente im Sicherheitsheader für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c4d1-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c4d1-133">Requirements</span></span>  
  
|<span data-ttu-id="4c4d1-134">MOF</span><span class="sxs-lookup"><span data-stu-id="4c4d1-134">MOF</span></span>|<span data-ttu-id="4c4d1-135">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4c4d1-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4c4d1-136">Namespace</span><span class="sxs-lookup"><span data-stu-id="4c4d1-136">Namespace</span></span>|<span data-ttu-id="4c4d1-137">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4c4d1-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c4d1-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c4d1-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
