---
title: "Beispiel für benutzerdefinierte Kompensationslogik"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3a9745c0cdd3a2d7050aed083d2eee5dfd4aaaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="custom-compensation-sample"></a>Beispiel für benutzerdefinierte Kompensationslogik
In diesem Beispiel wird gezeigt, wie <xref:System.Activities.Statements.CompensableActivity> und der zugehörige Kompensierungshandler zur Definition benutzerdefinierter Kompensierungslogik verwendet werden. Das Szenario in diesem Beispiel ist eine LKW-Vermietung.  
  
## <a name="sample-details"></a>Beispieldetails  
 Die folgenden Schritte werden simuliert:  
  
1.  Der Benutzer fordert Mietangebote für ein bestimmtes Datum an.  
  
2.  Drei LKW-Unternehmen werden kontaktiert und drei Angebote bereitgestellt.  
  
3.  Der Benutzer wählt ein Angebot aus und führt die Bestellung per Kreditkarte durch.  
  
4.  Die Anwendung bricht die anderen beiden Angebote ab.  
  
5.  Die Anwendung erhebt eine Dienstgebühr, die für Benutzer ohne Premium-Konto nicht erstattet werden kann, wenn eine Stornierung zehn Tage oder weniger vor dem reservierten Termin erfolgt.  
  
6.  Die Anwendung stellt die LKW-Mietgebühr in Rechnung.  
  
7.  Die Anwendung wartet bis zum reservierten Datum bzw. bis sich der Kunde entscheidet, den Reservierungsvorgang abzubrechen.  
  
8.  Wenn der Kunde den Reservierungsvorgang abbricht, wird der benutzerdefinierte <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>-Code nach der folgenden Logik ausführt:  
  
    1.  Wenn der Kunde nicht über ein Premium-Konto verfügt und die Reservierung weniger als zehn Tage vor dem reservierten Datum storniert, wird die Dienstgebühr in Rechnung gestellt. Andernfalls erstattet die Anwendung die Dienstgebühr.  
  
    2.  Die weiteren kompensierbaren Aktivitäten (LKW-Bestellung + LKW-Gebühr) werden nach der Standardkompensierungslogik ausgeführt, d. h. in umgekehrter Reihenfolge.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "CustomCompensation.sln". Sie befindet sich im Verzeichnis \WF\Basic\Compensation\CustomCompensation.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Anwendung auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`  
  
## <a name="see-also"></a>Siehe auch
