---
title: Verarbeiten von Transaktionen
description: Überprüfen Sie die Transaktionsverarbeitung in .net. Transaktionen stellen sicher, dass datenorientierte Ressourcen nicht dauerhaft aktualisiert werden, es sei denn, alle Vorgänge wurden erfolgreich abgeschlossen.
ms.date: 03/30/2017
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
ms.openlocfilehash: 30d69c55d968865cc80b8633bdbc2442f6d216de
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141913"
---
# <a name="transaction-processing"></a>Verarbeiten von Transaktionen
Wenn Sie ein Buch in einem Online-Buchladen kaufen, geben Sie Geld (in Form eines Guthabens) im Tausch für ein Buch. Wenn Sie über ein ausreichendes Guthaben verfügen, wird durch eine Reihe verbundener Vorgänge sichergestellt, dass Sie Ihr Buch erhalten und dem Buchladen der Betrag gutgeschrieben wird. Wenn aber während des Austauschs ein einzelner Vorgang in der Reihe fehlschlägt, schlägt der gesamte Austausch fehl. Sie erhalten das Buch nicht, und die Buchhandlung bekommt kein Geld.  
  
 Die Technologie, die dafür sorgt, dass der Vorgang ausgeglichen und vorhersagbar abläuft, wird als Transaktionsverarbeitung bezeichnet. Transaktionen stellen sicher, dass datenbezogene Ressourcen nicht ständig aktualisiert werden, sondern erst, wenn alle Vorgänge innerhalb der Transaktionseinheit erfolgreich abgeschlossen wurden. Indem ein Satz verbundener Vorgänge zu einer Einheit zusammengefasst wird, die als Ganzes erfolgreich durchgeführt wird oder fehlschlägt, wird die Wiederherstellung nach einem Fehler vereinfacht und die Anwendung zuverlässiger.  
  
 Systeme zur Transaktionsverarbeitung bestehen aus Computerhardware und -software, die eine transaktionsorientierte Anwendung hosten. Die Anwendung führt die Routinetransaktionen aus, die für Geschäftsabläufe notwendig sind. Beispiele dafür sind unter anderem Systeme, die Bestelleingänge, Flugticketreservierungen, Lohn- und Gehaltsabrechnungen, Mitarbeiterdatensätze, Fertigungs- und Versanddaten verwalten.  
  
 In diesem Abschnitt erhalten Sie sowohl allgemeine Informationen über die Transaktionsverarbeitung als auch spezifische Informationen darüber, wie Transaktionsanwendungen und Ressourcen-Manager mit Microsoft .NET Framework erstellt werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Transaktionsgrundlagen](transaction-fundamentals.md)  
 Bietet eine Einführung in grundlegende Transaktionsverarbeitungsbegriffe und -vorgänge.  
  
 [Von System.Transactions bereitgestellte Funktionen](features-provided-by-system-transactions.md)  
 Erläutert, wie Sie Funktionen in System.Transactions verwenden können, um eine eigene Transaktionsanwendung zu erstellen.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Transactions>  
 Stellt Klassen bereit, mit denen der Code an Transaktionen teilnehmen kann. Die Klassen unterstützen Transaktionen mit mehreren verteilten Teilnehmern, mehreren Phasenbenachrichtigungen und dauerhaften Eintragungen.
