---
title: 'Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 20db0ef427a5e791bd6b8dcef90bf7911ae0d4a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343479"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts
Windows Communication Foundation (WCF) verwendet einen Windows-Dienst, der den Net.TCP-Portfreigabedienst aufgerufen, um die gemeinsame Nutzung von TCP-Ports für mehrere Prozesse. Dieser Dienst wird als Teil von WCF installiert, aber der Dienst nicht als Sicherheitsmaßnahme standardmäßig aktiviert ist und daher muss manuell aktiviert werden vor der ersten Verwendung. In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.  
  
 Nachdem Sie den Net.TCP-Portfreigabedienst aktivieren und starten Sie ihn manuell, finden Sie unter [Vorgehensweise: Konfigurieren eines WCF-Diensts, um die Portfreigabe verwenden](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) Informationen dazu, wie Sie den Dienst zum Verwenden dieses Diensts zu konfigurieren.  
  
 Ein Beispiel mit net.tcp:// Anschlussfreigabe finden Sie unter den [Beispiel Net.TCP-Portfreigabe](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>So aktivieren Sie den Net.TCP-Portfreigabedienst mit MMC  
  
1. Öffnen Sie im Startmenü der Diensteverwaltungskonsole, entweder indem Sie ein Eingabeaufforderungsfenster öffnen und Folgendes eingeben `services.msc` oder indem Sie auf Ausführen klicken und eingeben `services.msc` in das Feld Öffnen.  
  
2. In der **Namen** mit der rechten Maustaste der Spalte mit der Liste der Dienste, die **Net.Tcp-Portfreigabedienst**, und wählen Sie **Eigenschaften** aus dem Menü.  
  
3. So aktivieren Sie den manuellen Start des Diensts in der **Eigenschaften** wählen Sie im Fenster der **allgemeine** Registerkarte und klicken Sie in der **Starttyp** Option manuell, und klicken Sie dann auf **Anwenden**.  
  
4. Um den Dienst im Statusbereich Dienst zu starten, klicken Sie auf die **starten** Schaltfläche. Der Dienststatus sollte jetzt "Gestartet" anzeigen.  
  
5. Um die Liste der Dienste zurückzukehren, klicken Sie auf die **OK**, und beenden Sie die MMC-Konsole.  
  
## <a name="example"></a>Beispiel  
  
## <a name="see-also"></a>Siehe auch

- [Net.TCP-Anschlussfreigabe](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [Konfigurieren des Net.TCP-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
