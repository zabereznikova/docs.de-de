---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 9da8f77ee8ea5dc8b22ac5c0cb5113e906c5dc78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262267"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="d9e8a-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="d9e8a-102">ServiceSecurityAuditBehavior</span></span>

<span data-ttu-id="d9e8a-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="d9e8a-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9e8a-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d9e8a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d9e8a-105">Methods</span></span>  

 <span data-ttu-id="d9e8a-106">Die ServiceSecurityAuditBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d9e8a-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d9e8a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d9e8a-107">Properties</span></span>  

 <span data-ttu-id="d9e8a-108">Die ServiceSecurityAuditBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d9e8a-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="d9e8a-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="d9e8a-109">AuditLogLocation</span></span>  

 <span data-ttu-id="d9e8a-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="d9e8a-110">Data type: string</span></span>  
  
 <span data-ttu-id="d9e8a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d9e8a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9e8a-112">Der Speicherort des Überwachungsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="d9e8a-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="d9e8a-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="d9e8a-113">MessageAuthenticationAuditLevel</span></span>  

 <span data-ttu-id="d9e8a-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="d9e8a-114">Data type: string</span></span>  
  
 <span data-ttu-id="d9e8a-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d9e8a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9e8a-116">Typ der Meldungsauthentifizierungsebene, die verwendet wird, um Überwachungsereignisse zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="d9e8a-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="d9e8a-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="d9e8a-117">ServiceAuthorizationAuditLevel</span></span>  

 <span data-ttu-id="d9e8a-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="d9e8a-118">Data type: string</span></span>  
  
 <span data-ttu-id="d9e8a-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d9e8a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9e8a-120">Typen von Autorisierungsereignissen, die im Überwachungsprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d9e8a-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="d9e8a-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="d9e8a-121">SuppressAuditFailure</span></span>  

 <span data-ttu-id="d9e8a-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d9e8a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d9e8a-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d9e8a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d9e8a-124">Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.</span><span class="sxs-lookup"><span data-stu-id="d9e8a-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e8a-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9e8a-125">Requirements</span></span>  
  
|<span data-ttu-id="d9e8a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d9e8a-126">MOF</span></span>|<span data-ttu-id="d9e8a-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d9e8a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d9e8a-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="d9e8a-128">Namespace</span></span>|<span data-ttu-id="d9e8a-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d9e8a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9e8a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9e8a-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
