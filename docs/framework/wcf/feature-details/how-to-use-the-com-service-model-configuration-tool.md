---
title: "Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools | Microsoft Docs"
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
  - "COM+ [WCF], Verwenden des Dienstmodell-Konfigurationstools"
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools
Nachdem Sie einen geeigneten Hosting\-Modus ausgewählt haben, verwenden Sie das COM\+\-Dienstmodell\-Konfigurations\-Befehlszeilentool \(ComSvcConfig.exe\) zur Konfigurierung der Anwendungsschnittstellen, die als Webdienste verfügbar gemacht werden.  
  
> [!NOTE]
>  Sie müssen über Administratorrechte verfügen, um die folgenden Aufgaben auszuführen zu können.  
  
 Wenn Sie **ComSvcConfig.exe** auf einem Windows 7\-Computer verwenden, um einen Webdienst für die Verwendung der neuesten Dienstmodellversion \(derzeit 4.5\) zu konfigurieren, führen Sie folgende Schritte aus:  
  
1.  Legen Sie den `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR`\-Registrierungsschlüssel auf den DWORD\-Wert 0x00000001 fest.  
  
2.  Führen Sie **comsvcconfig.exe** aus.  
  
3.  Legen Sie den in Schritt 1 festgelegten Registrierungsschlüssel wieder auf den ursprünglichen Wert fest, oder löschen Sie ihn, wenn er nicht vorhanden war.  
  
> [!IMPORTANT]
>  Es ist wichtig, diesen Registrierungsschlüssel wieder zurückzuversetzen, weil er einenKompatibilitätsschlüssel darstellt.Wird diese Änderung nicht rückgängig gemacht, können Probleme mit anderen .NET\-Anwendungen auftreten, die auf dem Computer ausgeführt werden\).  
  
> [!WARNING]
>  Wenn Sie **\/install** für **ComSvcConfig.exe** auf einem Windows 8\-Computer verwenden, wird in einem Dialogfeld eine mit der folgenden vergleichbare Meldung ausgegeben, wenn .NET Framework 3.5 nicht installiert ist: "Von einer App auf dem PC wird das folgende Windows\-Feature benötigt: .NET Framework 3.5 \(umfasst .NET 2.0 und .NET 3.0".Dieses Dialogfeld kann ignoriert werden.Alternativ können Sie den **OnlyUseLatestCLR**\-Registrierungsschlüssel auf den DWORD\-Wert 0x00000001 festlegen.  
  
### Um mithilfe des COM\+\-Hostingmodus eine Schnittstelle zu der Gruppe von Schnittstellen hinzuzufügen, die als Webdienste verfügbar gemacht werden sollen.  
  
-   Führen Sie ComSvcConfig mithilfe der `/install`\- und der `/hosting:complus`\-Optionen aus, wie im folgenden Beispiel gezeigt.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     Der Befehl fügt die `IFinances`\-Schnittstelle der `ItemOrders.IFinancial`\-Komponente \(aus der OnlineStore\-COM\+\-Anwendung\) zu der Gruppe von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden.Der Dienst verwendet den COM\+\-Hostingmodus und erfordert deshalb eine explizite Anwendungsaktivierung.  
  
     Obwohl das Sternchenzeichen \(\*\) als Platzhalter für die Komponente und die Schnittstelle verwendet werden kann, sollten Sie es vermeiden, da Sie möglicherweise nur ausgewählte Funktionen als Webdienst verfügbar machen möchten.Bei der Ausführung mit einer künftigen Version dieser Komponente kann die Verwendung des Platzhalters unbeabsichtigt Schnittstellen verfügbar machen, die noch nicht vorhanden waren, als die Konfigurationssyntax festgelegt wurde.  
  
     Die Option für die ausführliche Ausgabe weist das Tool an, zusätzlich zu Fehlern Warnungen anzuzeigen.  
  
     Der Vertrag für den verfügbar gemachten Dienst enthält alle Methoden aus der `IFinances`\-Schnittstelle.  
  
### So fügen Sie der Gruppe von Schnittstellen, die als Webdienste verfügbar gemacht werden sollen, nur bestimmte Methoden einer Schnittstelle mithilfe des COM\+\-Hostingmodus hinzu  
  
-   Führen Sie ComSvcConfig mithilfe der `/install`\- und der `/hosting:complus`\-Optionen mit expliziter Benennung der erforderlichen Methoden aus, wie im folgenden Beispiel gezeigt.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     Der Befehl fügt nur die `Credit`\- und die `Debit`\-Methode der `IFinances`\-Schnittstelle als Vorgänge zu dem verfügbar gemachten Dienstvertrag hinzu.Alle anderen Methoden der Schnittstelle erscheinen nicht im Vertrag und können von Webdienstclients nicht aufgerufen werden.  
  
### So fügen Sie einer Gruppe von Schnittstellen, die als Webdienste verfügbar gemacht werden sollen, eine Schnittstelle mithilfe des Webhostingmodus hinzu  
  
-   Führen Sie ComSvcConfig mithilfe der `/install`\- und der `/hosting:was`\-Option aus, wie im folgenden Beispiel gezeigt.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     Der Befehl fügt die `IStockLevels`\-Schnittstelle der `ItemInventory.Warehouse`\-Komponente \(aus der OnlineWarehouse\-COM\+\-Anwendung\) zu der Gruppe von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden.Statt in COM\+ wird der Dienst im virtuellen OnlineWarehouse\-Verzeichnis von IIS im Internet gehostet, und folglich wird die Anwendung automatisch bei Bedarf aktiviert.  
  
     Um die im Internet gehostete prozessinterne Konfiguration zu verwenden, muss die COM\+\-Anwendung mithilfe der Verwaltungskonsole Komponentendienste so konfiguriert werden, dass sie als Library\-Anwendung ausgeführt wird.Anwendungen, die als Serveranwendungen konfiguriert werden, werden standardmäßig im Internet gehostet und bewirken einen Prozesshop für die Verarbeitung jeder Anforderung.  
  
     Die `/mex`\-Option fügt einen zusätzlichen Metadatenaustausch\-Dienstendpunkt \(MEX oder Metadata Exchange\) hinzu, der denselben Transport verwendet wie der Dienstendpunkt der Anwendung, um Clients beim Abrufen einer Vertragsdefinition vom Dienst zu unterstützen.  
  
### Entfernen eines Webdiensts aus einer angegebenen Schnittstelle  
  
-   Führen Sie ComSvcConfig mithilfe der `/uninstall`\-Optionen aus, wie im folgenden Beispiel gezeigt.  
  
    ```  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     Der Befehl entfernt die `IFinances`\-Schnittstelle in der `ItemOrders.Financial`\-Komponente \(aus der OnlineStore\-COM\+\-Anwendung\).  
  
### So listen Sie zurzeit verfügbare Schnittstellen auf  
  
-   Führen Sie ComSvcConfig mithilfe der `/list`\-Option aus, wie im folgenden Beispiel gezeigt.  
  
    ```  
    ComSvcConfig.exe /list  
    ```  
  
     Der Befehl listet die derzeit verfügbaren Schnittstellen zusammen mit den entsprechenden Adress\- und Bindungsdetails auf, deren Gültigkeitsbereich der lokale Computer ist.  
  
### So listen Sie bestimmte zurzeit verfügbare Schnittstellen auf  
  
-   Führen Sie ComSvcConfig mithilfe der `/list`\-Optionen aus, wie im folgenden Beispiel gezeigt:  
  
    ```  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     Der Befehl listet derzeit verfügbare COM\+\-gehostete Schnittstellen zusammen mit den entsprechenden Adress\- und Bindungsdetails für die OnlineStore\-COM\+\-Anwendung auf dem lokalen Computer auf.  
  
### So zeigen Sie Hilfe in den Optionen an, die mit dem Hilfsprogramm verwendet werden können  
  
-   Führen Sie ComSvcConfig mithilfe der \/?\-Option aus, wie im folgenden Beispiel gezeigt.  
  
    ```  
    ComSvcConfig.exe /?  
  
    ```  
  
## Siehe auch  
 [Übersicht über die Integration von COM\+\-Anwendungen](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)