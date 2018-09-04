---
title: Benutzerdefinierte Überwachungsdatensätze
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: ef3c20890f33f3ffd07a9c88de863e1ebe24851f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520184"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="f7af6-102">Benutzerdefinierte Überwachungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="f7af6-102">Custom Tracking Records</span></span>
<span data-ttu-id="f7af6-103">In diesem Thema wird veranschaulicht, wie benutzerdefinierte Überwachungsdatensätze erstellt und mit Daten gefüllt werden, die mit den Datensätzen ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7af6-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>  
  
## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="f7af6-104">Ausgeben von benutzerdefinierten Nachverfolgungsdatensätzen</span><span class="sxs-lookup"><span data-stu-id="f7af6-104">Emitting Custom Tracking Records</span></span>  
 <span data-ttu-id="f7af6-105">Eine Codeaktivität kann benutzerdefinierte Nachverfolgungsdatensätze ausgeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7af6-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 <span data-ttu-id="f7af6-106">Ein <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekt wird in einer Codeaktivität ausgegeben, indem die <xref:System.Activities.NativeActivityContext.Track%2A>-Methode für den `ActvityContext` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f7af6-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActvityContext`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7af6-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7af6-107">See Also</span></span>  
 [<span data-ttu-id="f7af6-108">Windows Server App Fabric-Überwachung</span><span class="sxs-lookup"><span data-stu-id="f7af6-108">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="f7af6-109">Überwachen von Anwendungen mit AppFabric</span><span class="sxs-lookup"><span data-stu-id="f7af6-109">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
