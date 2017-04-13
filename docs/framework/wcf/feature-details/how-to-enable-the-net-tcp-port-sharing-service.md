---
title: "Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anschlussfreigabe [WCF]"
  - "Aktivierungsdienste [WCF]"
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet einen Windows-Dienst namens NET.TCP-Portfreigabedienst, der die gemeinsame Nutzung eines TCP-Anschlusses durch mehrere Prozesse vereinfacht. Dieser Dienst wird als Teil von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] installiert, ist jedoch aus Sicherheitsgründen nicht standardmäßig aktiviert. Daher muss er vor der ersten Verwendung manuell aktiviert werden. In diesem Thema wird beschrieben, wie Sie den NET.TCP-Portfreigabedienst mit dem Microsoft Management Console (MMC)-Snap-In konfigurieren können.  
  
 Nachdem Sie den Net.TCP-Portfreigabedienst aktivieren und starten Sie ihn manuell, finden Sie unter [Gewusst wie: Konfigurieren eines WCF-Diensts, um die Portfreigabe verwenden](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) für Informationen dazu, wie Sie den Dienst zum Verwenden dieses Diensts konfigurieren.  
  
 Ein Beispiel mit net.tcp:// Portfreigabe finden Sie unter der [Beispiel Net.TCP-Portfreigabe](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>So aktivieren Sie den Net.TCP-Portfreigabedienst mit MMC  
  
1.  Öffnen Sie im Startmenü der Diensteverwaltungskonsole entweder, öffnen ein Eingabeaufforderungsfenster und geben `services.msc` oder indem Sie auf Ausführen, und geben Sie `services.msc` in das Feld Öffnen.  
  
2.  In der **Namen** Spalte der Liste der Dienste mit der rechten Maustaste die **Net.Tcp-Portfreigabedienst**, und wählen Sie **Eigenschaften** aus dem Menü.  
  
3.  So aktivieren Sie den manuellen Start des Diensts, in der **Eigenschaften** aus der **allgemeine** Registerkarte und in der **Starttyp** wählen manuell, und klicken Sie dann auf **übernehmen**.  
  
4.  Um den Dienst im Statusbereich Dienst zu starten, klicken Sie auf die **Start** Schaltfläche. Der Dienststatus sollte jetzt "Gestartet" anzeigen.  
  
5.  Um die Liste der Dienste zurückzukehren, klicken Sie auf die **OK**, und schließen Sie die MMC-Konsole.  
  
## <a name="example"></a>Beispiel  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 [Net.TCP-Portfreigabedienst](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)   
 [Konfigurieren der Net.TCP-Portfreigabedienst](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)