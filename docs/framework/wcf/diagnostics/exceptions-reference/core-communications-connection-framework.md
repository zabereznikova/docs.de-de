---
title: 'Kernkommunikation: Verbindungsframework'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: a3f52ac82c2bf09ded504e412d7f216dd0b39959
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998685"
---
# <a name="core-communications-connection-framework"></a>Kernkommunikation: Verbindungsframework
Dieses Thema enthält alle Ausnahmen, die vom Framework für Windows Communication Foundation (WCF)-Verbindung.  
  
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
