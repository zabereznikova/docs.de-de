---
title: 'Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9934d198b8f3e30a4dc350c968263851ebeab1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet einen Windows-Dienst namens NET.TCP-Portfreigabedienst, der die gemeinsame Nutzung eines TCP-Anschlusses durch mehrere Prozesse vereinfacht. Dieser Dienst wird als Teil von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] installiert, ist jedoch aus Sicherheitsgründen nicht standardmäßig aktiviert. Daher muss er vor der ersten Verwendung manuell aktiviert werden. In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.  
  
 Nachdem Sie den Net.TCP-Portfreigabedienst aktivieren und starten Sie ihn manuell, finden Sie unter [Vorgehensweise: Konfigurieren eines WCF-Diensts, um die Portfreigabe verwenden](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) für Informationen dazu, wie Sie den Dienst zum Verwenden dieses Diensts konfigurieren.  
  
 Ein Beispiel, das net.tcp:// Portfreigabe verwendet, finden Sie unter der [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>So aktivieren Sie den Net.TCP-Portfreigabedienst mit MMC  
  
1.  Öffnen Sie über das Startmenü Diensteverwaltungskonsole, entweder indem Sie ein Eingabeaufforderungsfenster öffnen und Folgendes eingeben: `services.msc` oder durch Ausführen öffnen und Folgendes eingeben: `services.msc` in das Feld Öffnen.  
  
2.  In der **Namen** Maustaste Spalte der Liste der Dienste, die **Net.Tcp-Portfreigabedienst**, und wählen Sie **Eigenschaften** aus dem Menü.  
  
3.  So aktivieren Sie den manuellen Start des Diensts, in der **Eigenschaften** wählen Sie im Fenster der **allgemeine** Registerkarte, und klicken Sie in der **Starttyp** Feld wählen manuell, und klicken Sie dann auf **Gelten**.  
  
4.  Um den Dienst im Statusbereich Dienst zu starten, klicken Sie auf die **starten** Schaltfläche. Der Dienststatus sollte jetzt "Gestartet" anzeigen.  
  
5.  Um zu der Liste der Dienste zurückzukehren, klicken Sie auf die **OK**, und beenden Sie die MMC-Konsole.  
  
## <a name="example"></a>Beispiel  
  
## <a name="see-also"></a>Siehe auch  
 [Net.TCP-Portfreigabe](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [Konfigurieren des Net.TCP-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
