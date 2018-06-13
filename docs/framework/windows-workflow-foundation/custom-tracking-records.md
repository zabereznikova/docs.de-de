---
title: Benutzerdefinierte Überwachungsdatensätze
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 6c68c08e5beacee30b517bf0c2bad3e83785409b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511334"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="0ff00-102">Benutzerdefinierte Überwachungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="0ff00-102">Custom Tracking Records</span></span>
<span data-ttu-id="0ff00-103">In diesem Thema wird veranschaulicht, wie benutzerdefinierte Überwachungsdatensätze erstellt und mit Daten gefüllt werden, die mit den Datensätzen ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0ff00-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>  
  
## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="0ff00-104">Ausgeben von benutzerdefinierten Nachverfolgungsdatensätzen</span><span class="sxs-lookup"><span data-stu-id="0ff00-104">Emitting Custom Tracking Records</span></span>  
 <span data-ttu-id="0ff00-105">Eine Codeaktivität kann benutzerdefinierte Nachverfolgungsdatensätze ausgeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff00-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 <span data-ttu-id="0ff00-106">Ein <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekt wird in einer Codeaktivität ausgegeben, indem die <xref:System.Activities.NativeActivityContext.Track%2A>-Methode für den `ActvityContext` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0ff00-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActvityContext`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff00-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ff00-107">See Also</span></span>  
 [<span data-ttu-id="0ff00-108">Windows Server App Fabric-Überwachung</span><span class="sxs-lookup"><span data-stu-id="0ff00-108">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="0ff00-109">Überwachen von Anwendungen mit AppFabric</span><span class="sxs-lookup"><span data-stu-id="0ff00-109">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
