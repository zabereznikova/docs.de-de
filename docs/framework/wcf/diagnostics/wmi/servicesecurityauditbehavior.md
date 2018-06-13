---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3adc721dd8ad0fb706e172373e5da70fe6032db6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485894"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="efe73-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="efe73-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="efe73-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="efe73-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efe73-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="efe73-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="efe73-105">Methods</span></span>  
 <span data-ttu-id="efe73-106">Die ServiceSecurityAuditBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="efe73-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="efe73-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="efe73-107">Properties</span></span>  
 <span data-ttu-id="efe73-108">Die ServiceSecurityAuditBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="efe73-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="efe73-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="efe73-109">AuditLogLocation</span></span>  
 <span data-ttu-id="efe73-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="efe73-110">Data type: string</span></span>  
  
 <span data-ttu-id="efe73-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="efe73-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efe73-112">Der Speicherort des Überwachungsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="efe73-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="efe73-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="efe73-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="efe73-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="efe73-114">Data type: string</span></span>  
  
 <span data-ttu-id="efe73-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="efe73-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efe73-116">Typ der Meldungsauthentifizierungsebene, die verwendet wird, um Überwachungsereignisse zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="efe73-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="efe73-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="efe73-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="efe73-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="efe73-118">Data type: string</span></span>  
  
 <span data-ttu-id="efe73-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="efe73-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efe73-120">Typen von Autorisierungsereignissen, die im Überwachungsprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="efe73-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="efe73-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="efe73-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="efe73-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="efe73-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="efe73-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="efe73-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efe73-124">Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.</span><span class="sxs-lookup"><span data-stu-id="efe73-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efe73-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efe73-125">Requirements</span></span>  
  
|<span data-ttu-id="efe73-126">MOF</span><span class="sxs-lookup"><span data-stu-id="efe73-126">MOF</span></span>|<span data-ttu-id="efe73-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="efe73-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="efe73-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="efe73-128">Namespace</span></span>|<span data-ttu-id="efe73-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="efe73-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efe73-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efe73-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
