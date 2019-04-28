---
title: 'Dienst: Nicht autorisierte Sicherheitsaufrufe'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: a38b5e0eb467a5cad698fd6e3e01c0adef825d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773336"
---
# <a name="service-security-calls-not-authorized"></a>Dienst: Nicht autorisierte Sicherheitsaufrufe
Indikatorname: Nicht autorisierte Sicherheitsaufrufe.  
  
## <a name="description"></a>Beschreibung  
 Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt. Er gibt an, dass die eingehende Nachricht von einem gültigen Benutzer stammt und ordnungsgemäß geschützt ist, der Benutzer jedoch nicht für die Durchführung spezifischer Aufgaben autorisiert ist.
