---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ea9c04c201ff022fcea54b81a998b7020fb2a836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="e972f-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="e972f-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="e972f-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="e972f-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e972f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e972f-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e972f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e972f-105">Methods</span></span>  
 <span data-ttu-id="e972f-106">Die ServiceSecurityAuditBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e972f-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e972f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e972f-107">Properties</span></span>  
 <span data-ttu-id="e972f-108">Die ServiceSecurityAuditBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e972f-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="e972f-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="e972f-109">AuditLogLocation</span></span>  
 <span data-ttu-id="e972f-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e972f-110">Data type: string</span></span>  
  
 <span data-ttu-id="e972f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e972f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e972f-112">Der Speicherort des Überwachungsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="e972f-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="e972f-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="e972f-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="e972f-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e972f-114">Data type: string</span></span>  
  
 <span data-ttu-id="e972f-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e972f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e972f-116">Typ der Meldungsauthentifizierungsebene, die verwendet wird, um Überwachungsereignisse zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="e972f-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="e972f-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="e972f-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="e972f-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e972f-118">Data type: string</span></span>  
  
 <span data-ttu-id="e972f-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e972f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e972f-120">Typen von Autorisierungsereignissen, die im Überwachungsprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="e972f-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="e972f-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="e972f-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="e972f-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e972f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e972f-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e972f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e972f-124">Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.</span><span class="sxs-lookup"><span data-stu-id="e972f-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e972f-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e972f-125">Requirements</span></span>  
  
|<span data-ttu-id="e972f-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e972f-126">MOF</span></span>|<span data-ttu-id="e972f-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e972f-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e972f-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="e972f-128">Namespace</span></span>|<span data-ttu-id="e972f-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e972f-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e972f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e972f-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
