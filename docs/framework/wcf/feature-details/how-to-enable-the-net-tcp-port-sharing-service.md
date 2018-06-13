---
title: 'Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 4b5a18e11d9fc15f23b5353883a63d838face58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490759"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts
Windows Communication Foundation (WCF) verwendet einen Windows-Dienst, der den Net.TCP-Portfreigabedienst aufgerufen, um zu vereinfachen, die gemeinsame Nutzung von TCP-Ports für mehrere Prozesse. Dieser Dienst wird im Rahmen des WCF installiert, aber der Dienst ist nicht standardmäßig aktiviert, als Sicherheitsmaßnahme und daher muss manuell aktiviert werden vor der ersten Verwendung. In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.  
  
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
