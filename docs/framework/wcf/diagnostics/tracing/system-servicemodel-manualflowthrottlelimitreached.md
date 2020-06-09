---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: bffa6361df5a50748f45aa3004f7a307ad516d7b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580488"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a>System.ServiceModel.ManualFlowThrottleLimitReached
System.ServiceModel.ManualFlowThrottleLimitReached  
  
## <a name="description"></a>BESCHREIBUNG  
 Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht. Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.  
  
 Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird. Eine spätere Änderung auf 0 (null) wird nicht verfolgt. Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
