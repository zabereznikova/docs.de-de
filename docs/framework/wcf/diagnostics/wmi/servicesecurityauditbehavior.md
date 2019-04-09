---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203508"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="6eecf-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="6eecf-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="6eecf-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="6eecf-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eecf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6eecf-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6eecf-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6eecf-105">Methods</span></span>  
 <span data-ttu-id="6eecf-106">Die ServiceSecurityAuditBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="6eecf-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6eecf-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6eecf-107">Properties</span></span>  
 <span data-ttu-id="6eecf-108">Die ServiceSecurityAuditBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="6eecf-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="6eecf-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="6eecf-109">AuditLogLocation</span></span>  
 <span data-ttu-id="6eecf-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="6eecf-110">Data type: string</span></span>  
  
 <span data-ttu-id="6eecf-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6eecf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6eecf-112">Der Speicherort des Überwachungsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="6eecf-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="6eecf-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="6eecf-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="6eecf-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="6eecf-114">Data type: string</span></span>  
  
 <span data-ttu-id="6eecf-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6eecf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6eecf-116">Typ der Meldungsauthentifizierungsebene, die verwendet wird, um Überwachungsereignisse zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="6eecf-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="6eecf-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="6eecf-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="6eecf-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="6eecf-118">Data type: string</span></span>  
  
 <span data-ttu-id="6eecf-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6eecf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6eecf-120">Typen von Autorisierungsereignissen, die im Überwachungsprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="6eecf-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="6eecf-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="6eecf-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="6eecf-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="6eecf-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="6eecf-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6eecf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6eecf-124">Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.</span><span class="sxs-lookup"><span data-stu-id="6eecf-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eecf-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6eecf-125">Requirements</span></span>  
  
|<span data-ttu-id="6eecf-126">MOF</span><span class="sxs-lookup"><span data-stu-id="6eecf-126">MOF</span></span>|<span data-ttu-id="6eecf-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6eecf-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6eecf-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="6eecf-128">Namespace</span></span>|<span data-ttu-id="6eecf-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6eecf-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6eecf-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eecf-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
