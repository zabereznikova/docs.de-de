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
# <a name="msmq"></a><span data-ttu-id="b75e2-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="b75e2-102">MSMQ</span></span>
<span data-ttu-id="b75e2-103">In einer MSMQ-Anwendung wird keine zusätzliche Aktivität vom in der Warteschlange stehenden Kanal zu MSMQ und von MSMQ zum in der Warteschlange stehenden Kanal übertragen.</span><span class="sxs-lookup"><span data-stu-id="b75e2-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="b75e2-104">Darüber hinaus werden die MSMQ-Nachrichten-ID und SOAP-Nachrichten-ID (zusammen mit der Aktivitäts-ID, falls vorhanden) als Teil der Ablaufverfolgungen in der Warteschlange stehender Kanäle bei einem Sendevorgang verfolgt.</span><span class="sxs-lookup"><span data-stu-id="b75e2-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="b75e2-105">Die MSMQ-Nachrichten-ID und SOAP-Nachrichten-ID (zusammen mit der Aktivitäts-ID, falls vorhanden) werden als Teil der Ablaufverfolgungen in der Warteschlange stehender Kanäle bei einem Empfangsvorgang verfolgt.</span><span class="sxs-lookup"><span data-stu-id="b75e2-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="b75e2-106">Die erforderlichen Übertragungen beim Empfangsvorgang werden ebenso wie ein anderer Transport ausgeführt (Vorgang Byteempfang->Nachrichtenverarbeitung).</span><span class="sxs-lookup"><span data-stu-id="b75e2-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
