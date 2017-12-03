---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15be4b6bfb84a0aa843e3d62861a9195e125a04e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="msmq"></a>MSMQ
In einer MSMQ-Anwendung wird keine zusätzliche Aktivität vom in der Warteschlange stehenden Kanal zu MSMQ und von MSMQ zum in der Warteschlange stehenden Kanal übertragen.  
  
 Darüber hinaus werden die MSMQ-Nachrichten-ID und SOAP-Nachrichten-ID (zusammen mit der Aktivitäts-ID, falls vorhanden) als Teil der Ablaufverfolgungen in der Warteschlange stehender Kanäle bei einem Sendevorgang verfolgt.  
  
 Die MSMQ-Nachrichten-ID und SOAP-Nachrichten-ID (zusammen mit der Aktivitäts-ID, falls vorhanden) werden als Teil der Ablaufverfolgungen in der Warteschlange stehender Kanäle bei einem Empfangsvorgang verfolgt.  
  
 Die erforderlichen Übertragungen beim Empfangsvorgang werden ebenso wie ein anderer Transport ausgeführt (Vorgang Byteempfang->Nachrichtenverarbeitung).
