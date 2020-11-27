---
title: 'Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts'
description: Erfahren Sie, wie Sie den NET TCP-Port Freigabe Dienst mithilfe von MMC zum Aktivieren von "net. TCP" konfigurieren, das standardmäßig deaktiviert ist.
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 7200d82e4a45ce9e36b2a4cec3d0c08e1a5f00ab
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265465"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts

Windows Communication Foundation (WCF) verwendet einen Windows-Dienst, der als net. TCP-Port Freigabe Dienst bezeichnet wird, um die Freigabe von TCP-Ports über mehrere Prozesse hinweg zu vereinfachen. Dieser Dienst wird als Teil von WCF installiert, aber der Dienst ist nicht standardmäßig als Sicherheitsmaßnahme aktiviert und muss vor der ersten Verwendung manuell aktiviert werden. In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.  
  
 Nachdem Sie den Net. TCP-Port Freigabe Dienst aktiviert und manuell gestartet haben, finden Sie unter Gewusst [wie: Konfigurieren eines WCF-Dienstanbieter](how-to-configure-a-wcf-service-to-use-port-sharing.md) für die Verwendung von Port Freigabe Informationen zum Konfigurieren des Dienstanbieter für die Verwendung dieses Dienstanbieter.  
  
 Ein Beispiel für die Verwendung von net. TCP://der Port Freigabe finden Sie unter [net. TCP-Port Freigabe Beispiel](../samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>So aktivieren Sie den Net.TCP-Portfreigabedienst mit MMC  
  
1. Öffnen Sie über das Startmenü die Dienste-Verwaltungskonsole, indem Sie ein Eingabe Aufforderungs Fenster öffnen und eingeben, `services.msc` oder indem Sie ausführen und `services.msc` in das Feld Öffnen eingeben.  
  
2. Klicken Sie in der Spalte **Name** der Liste der Dienste mit der rechten Maustaste auf den **net. TCP-Port Freigabe Dienst**, und wählen Sie im Menü **Eigenschaften** aus.  
  
3. Um das manuelle Starten des Dienstanbieter zu aktivieren, wählen Sie im **Eigenschaften** Fenster die Registerkarte **Allgemein** aus, und wählen Sie im Feld **Starttyp** die Option manuell aus, **und klicken Sie dann auf über** nehmen.  
  
4. Um den Dienst zu starten, klicken Sie im Bereich Dienststatus auf die Schaltfläche **Start** . Der Dienststatus sollte jetzt "Gestartet" anzeigen.  
  
5. Um zur Liste der Dienste zurückzukehren, klicken Sie auf **OK**, und beenden Sie die MMC-Konsole.  
  
## <a name="example"></a>Beispiel  
  
## <a name="see-also"></a>Weitere Informationen

- [Net.TCP-Anschlussfreigabe](net-tcp-port-sharing.md)
- [Konfigurieren des Net.TCP-Portfreigabediensts](configuring-the-net-tcp-port-sharing-service.md)
