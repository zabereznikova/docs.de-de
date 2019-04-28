---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663725"
---
# <a name="msmq"></a>MSMQ
In einer MSMQ-Anwendung wird keine zusätzliche Aktivität vom in der Warteschlange stehenden Kanal zu MSMQ und von MSMQ zum in der Warteschlange stehenden Kanal übertragen.  
  
 Darüber hinaus werden die MSMQ-Nachrichten-ID und SOAP-Nachrichten-ID (zusammen mit der Aktivitäts-ID, falls vorhanden) als Teil der Ablaufverfolgungen in der Warteschlange stehender Kanäle bei einem Sendevorgang verfolgt.  
  
 Die MSMQ-Nachrichten-ID und SOAP-Nachrichten-ID (zusammen mit der Aktivitäts-ID, falls vorhanden) werden als Teil der Ablaufverfolgungen in der Warteschlange stehender Kanäle bei einem Empfangsvorgang verfolgt.  
  
 Die erforderlichen Übertragungen beim Empfangsvorgang werden ebenso wie ein anderer Transport ausgeführt (Vorgang Byteempfang->Nachrichtenverarbeitung).
