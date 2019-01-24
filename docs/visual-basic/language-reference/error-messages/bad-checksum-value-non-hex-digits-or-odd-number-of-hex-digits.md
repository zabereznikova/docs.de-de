---
title: Ungültiger Prüfsummenwert, keine hexadezimalen Ziffern oder ungerade Anzahl von hexadezimalen Ziffern.
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 211f07e7c9dbc7e0583272d46c493ad99628d283
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724108"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>Ungültiger Prüfsummenwert, keine hexadezimalen Ziffern oder ungerade Anzahl von hexadezimalen Ziffern.
Ein Prüfsummenwert enthält ungültige hexadezimale Ziffern oder hat eine ungerade Anzahl an Ziffern.  
  
 Wenn ASP.NET eine Visual Basic-Quelldatei (Dateierweiterung .vb) erstellt, berechnet es die Prüfsumme und platziert sie in einer ausgeblendeten Quelldatei, die mit `#externalchecksum` gekennzeichnet wird. Ein Benutzer, der eine VB-Datei generiert, hat die Möglichkeit, dies selbst zu übernehmen, doch dieser Prozess sollte lieber intern ausgeführt werden.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42033  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Wenn ASP.NET die Visual Basic-Quelldatei generiert, starten Sie den Projektbuild neu.  
  
2.  Wenn diese Warnung auch nach einem Neustart ausgegeben wird, installieren Sie ASP.NET neu, und führen Sie den Vorgang mit dem Build erneut aus.  
  
3.  Wenn auch dann die Warnung weiterhin besteht oder wenn Sie nicht ASP.NET verwenden, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch

- [ASP.NET Overview (Übersicht über ASP.NET)](/aspnet/overview)
- [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
