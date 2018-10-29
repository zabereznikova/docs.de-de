---
title: Nicht autorisierte Sicherheitsaufrufe
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
ms.openlocfilehash: 492886a8e0083e8993b68ad710229113faf79e8d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198391"
---
# <a name="security-calls-not-authorized"></a>Nicht autorisierte Sicherheitsaufrufe
Indikatorname: Security Calls Not Authorized.  
  
## <a name="description"></a>Beschreibung  
 Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt. Er gibt an, dass die eingehende Nachricht von einem gültigen Benutzer stammt und ordnungsgemäß geschützt ist, der Benutzer jedoch nicht für die Durchführung spezifischer Aufgaben autorisiert ist.
