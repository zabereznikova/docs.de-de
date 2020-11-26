---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235115"
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused

System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>BESCHREIBUNG  

 Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.  
  
 Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:  
  
- ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.  
  
- Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.  
  
- Der Synchronisierungskontext ist nicht aktuell.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
