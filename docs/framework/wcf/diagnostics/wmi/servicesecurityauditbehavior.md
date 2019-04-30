---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956896"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="bcf38-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="bcf38-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="bcf38-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="bcf38-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcf38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcf38-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bcf38-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bcf38-105">Methods</span></span>  
 <span data-ttu-id="bcf38-106">Die ServiceSecurityAuditBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="bcf38-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bcf38-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bcf38-107">Properties</span></span>  
 <span data-ttu-id="bcf38-108">Die ServiceSecurityAuditBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="bcf38-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="bcf38-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="bcf38-109">AuditLogLocation</span></span>  
 <span data-ttu-id="bcf38-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bcf38-110">Data type: string</span></span>  
  
 <span data-ttu-id="bcf38-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bcf38-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf38-112">Der Speicherort des Überwachungsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="bcf38-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="bcf38-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="bcf38-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="bcf38-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bcf38-114">Data type: string</span></span>  
  
 <span data-ttu-id="bcf38-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bcf38-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf38-116">Typ der Meldungsauthentifizierungsebene, die verwendet wird, um Überwachungsereignisse zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="bcf38-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="bcf38-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="bcf38-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="bcf38-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bcf38-118">Data type: string</span></span>  
  
 <span data-ttu-id="bcf38-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bcf38-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf38-120">Typen von Autorisierungsereignissen, die im Überwachungsprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="bcf38-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="bcf38-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="bcf38-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="bcf38-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="bcf38-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcf38-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bcf38-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf38-124">Boolescher Wert, der das Verhalten für das Unterdrücken von Fehlern beim Schreiben in das Überwachungsprotokoll angibt.</span><span class="sxs-lookup"><span data-stu-id="bcf38-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcf38-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bcf38-125">Requirements</span></span>  
  
|<span data-ttu-id="bcf38-126">MOF</span><span class="sxs-lookup"><span data-stu-id="bcf38-126">MOF</span></span>|<span data-ttu-id="bcf38-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bcf38-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bcf38-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="bcf38-128">Namespace</span></span>|<span data-ttu-id="bcf38-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bcf38-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcf38-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcf38-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
