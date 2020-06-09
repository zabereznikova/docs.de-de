---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: e11b376924ee74e5d0d67da0cac59af41655dc44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594074"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Empfangen einer Nachricht über einen HTTP-Kanal fehlgeschlagen.  
  
## <a name="description"></a>BESCHREIBUNG  
 Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden. In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http-Anforderung kein kompatibler Listener gefunden wird und die HTTP-Anforderung gelöscht wird. Dies kann der Fall sein, weil das http-Verb der Anforderung von keinem http-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war. Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
