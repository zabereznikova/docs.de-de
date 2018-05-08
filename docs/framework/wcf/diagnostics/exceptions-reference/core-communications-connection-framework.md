---
title: 'Kernkommunikation: Verbindungsframework'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: a3f52ac82c2bf09ded504e412d7f216dd0b39959
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="core-communications-connection-framework"></a>Kernkommunikation: Verbindungsframework
Dieses Thema enthält alle Ausnahmen, die von Windows Communication Foundation (WCF)-Verbindungsframework generiert.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|CloseTimedOut|Das Zeitlimit der Close-Methode ist nach der angegebenen Zeit überschritten worden. Erhöhen Sie den Timeoutwert, der für den Aufruf der Close-Methode übergeben wird, oder erhöhen Sie den CloseTimeout-Wert in der Bindung. Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.|  
|ContentTypeMismatch|Der angegebene Inhaltstyp wurde an einen Dienst gesendet, der den angegebenen Typ erwartet hat. Möglicherweise besteht keine Übereinstimmung zwischen Client- und Dienstbindung.|  
|DuplexChannelAbortedDuringOpen|Der Duplexkanal für die angegebene Verbindung wurde während des Open-Vorgangs beendet. |  
|FramingValueNotAvailable|Auf den Wert kann nicht zugegriffen werden, da er nicht vollständig decodiert wurde.|  
|OperationAbortedDuringConnectionEstablishment|Der Vorgang wurde beendet, während die angegebene Verbindung hergestellt wurde.|  
|ReceiveTimedOut2|Das Zeitlimit des Empfangsvorgangs ist nach der angegebenen Zeit überschritten worden. Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.|  
|SendCannotBeCalledAfterCloseOutputSession|Sie können keine Nachrichten für einen Kanal senden, nachdem CloseOutputSession aufgerufen wurde.|
