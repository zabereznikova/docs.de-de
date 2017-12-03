---
title: 'Kernkommunikation: Verbindungsframework'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 878d2b01ee22d339115925e101f7349ecd5207bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-connection-framework"></a>Kernkommunikation: Verbindungsframework
In diesem Thema sind alle vom [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Verbindungsframework erzeugten Ausnahmen aufgeführt.  
  
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
