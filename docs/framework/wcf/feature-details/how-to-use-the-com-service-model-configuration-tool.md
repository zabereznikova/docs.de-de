---
title: 'Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: 2d21ec8ccf84a7c9af235af8e0afd444044cf81b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729386"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a>Vorgehensweise: Verwenden des COM+-Dienstmodell-Konfigurationstools

Nachdem Sie einen geeigneten Hosting-Modus ausgewählt haben, verwenden Sie das COM+-Dienstmodell-Konfigurations-Befehlszeilentool (ComSvcConfig.exe) zur Konfigurierung der Anwendungsschnittstellen, die als Webdienste verfügbar gemacht werden.

> [!NOTE]
> Sie müssen über Administratorrechte verfügen, um die folgenden Aufgaben auszuführen zu können.

 Wenn Sie ComSvcConfig.exe auf einem Windows 7-Computer verwenden, um einen Webdienst für die Verwendung der neuesten Dienstmodellversion (derzeit 4.5) zu konfigurieren, führen Sie folgende Schritte aus:

1. Legen Sie den Registrierungsschlüssel  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` auf den DWORD-Wert 0x00000001 fest.

2. Führen Sie comsvcconfig.exe aus.

3. Legen Sie den in Schritt 1 festgelegten Registrierungsschlüssel wieder auf den ursprünglichen Wert fest, oder löschen Sie ihn, wenn er nicht vorhanden war.

> [!IMPORTANT]
> Es ist wichtig, diesen Registrierungsschlüssel wieder zurückzuversetzen, weil er einen Kompatibilitätsschlüssel darstellt. Wird diese Änderung nicht rückgängig gemacht, können Probleme mit anderen .NET-Anwendungen auftreten, die auf dem Computer ausgeführt werden).

> [!WARNING]
> Wenn ComSvcConfig.exe/install auf einem Computer mit Windows 8 verwendet wird, wird ein Dialogfeld mit dem Hinweis angezeigt, dass für eine APP auf Ihrem PC Folgendes Windows-Feature erforderlich ist: .NET Framework 3,5 (enthält .NET 2,0 und .NET 3,0), wenn .NET Framework 3,5 nicht installiert ist. Dieses Dialogfeld kann ignoriert werden. Alternativ können Sie den OnlyUseLatestCLR-Registrierungsschlüssel auf den DWORD-Wert 0x00000001 festlegen.

## <a name="add-an-interface-using-the-com-hosting-mode"></a>Hinzufügen einer Schnittstelle mithilfe des COM+-Hostingmodus

- Führen Sie ComSvcConfig mithilfe der `/install`- und der `/hosting:complus`-Optionen aus, wie im folgenden Beispiel gezeigt.

    ```console
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose
    ```

     Der Befehl fügt die `IFinances`-Schnittstelle der `ItemOrders.IFinancial`-Komponente (aus der OnlineStore-COM+-Anwendung) zu der Gruppe von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden. Der Dienst verwendet den COM+-Hostingmodus und erfordert deshalb eine explizite Anwendungsaktivierung.

     Das Platzhalter Sternchen ( \* ) kann für die-Komponente und die-Schnittstelle verwendet werden, sollten Sie jedoch nicht verwenden, da Sie möglicherweise nur ausgewählte Funktionen als Webdienst verfügbar machen möchten. Bei der Ausführung mit einer künftigen Version dieser Komponente kann die Verwendung des Platzhalters unbeabsichtigt Schnittstellen verfügbar machen, die noch nicht vorhanden waren, als die Konfigurationssyntax festgelegt wurde.

     Die Option für die ausführliche Ausgabe weist das Tool an, zusätzlich zu Fehlern Warnungen anzuzeigen.

     Der Vertrag für den verfügbar gemachten Dienst enthält alle Methoden aus der `IFinances`-Schnittstelle.

## <a name="add-specific-methods-from-an-interface-using-the-com-hosting-mode"></a>Hinzufügen spezifischer Methoden aus einer Schnittstelle mithilfe des COM+-Hostingmodus

- Führen Sie ComSvcConfig mithilfe der `/install`- und der `/hosting:complus`-Optionen mit expliziter Benennung der erforderlichen Methoden aus, wie im folgenden Beispiel gezeigt.

    ```console
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose
    ```

     Der Befehl fügt nur die `Credit`- und die `Debit`-Methode der `IFinances`-Schnittstelle als Vorgänge zu dem verfügbar gemachten Dienstvertrag hinzu. Alle anderen Methoden der Schnittstelle erscheinen nicht im Vertrag und können von Webdienstclients nicht aufgerufen werden.

## <a name="add-an-interface-using-the-web-hosting-mode"></a>Hinzufügen einer Schnittstelle mithilfe des Webhostingmodus

- Führen Sie ComSvcConfig mithilfe der `/install`- und der `/hosting:was`-Option aus, wie im folgenden Beispiel gezeigt.

    ```console
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose
    ```

     Der Befehl fügt die `IStockLevels`-Schnittstelle der `ItemInventory.Warehouse`-Komponente (aus der OnlineWarehouse-COM+-Anwendung) zu der Gruppe von Schnittstellen hinzu, die als Webdienste verfügbar gemacht werden. Statt in COM+ wird der Dienst im virtuellen OnlineWarehouse-Verzeichnis von IIS im Internet gehostet, und folglich wird die Anwendung automatisch bei Bedarf aktiviert.

     Um die im Internet gehostete prozessinterne Konfiguration zu verwenden, muss die COM+-Anwendung mithilfe der Verwaltungskonsole Komponentendienste so konfiguriert werden, dass sie als Library-Anwendung ausgeführt wird. Anwendungen, die als Serveranwendungen konfiguriert werden, werden standardmäßig im Internet gehostet und bewirken einen Prozesshop für die Verarbeitung jeder Anforderung.

     Die `/mex`-Option fügt einen zusätzlichen Metadatenaustausch-Dienstendpunkt (MEX oder Metadata Exchange) hinzu, der denselben Transport verwendet wie der Dienstendpunkt der Anwendung, um Clients beim Abrufen einer Vertragsdefinition vom Dienst zu unterstützen.

## <a name="remove-a-web-service-for-a-specified-interface"></a>Entfernen eines Webdiensts für eine angegebene Schnittstelle

- Führen Sie ComSvcConfig mithilfe der `/uninstall`-Optionen aus, wie im folgenden Beispiel gezeigt:

    ```console
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus
    ```

     Der Befehl entfernt die `IFinances`-Schnittstelle in der `ItemOrders.Financial`-Komponente (aus der OnlineStore-COM+-Anwendung).

## <a name="list-currently-exposed-interfaces"></a>Auflisten aktuell verfügbare Schnittstellen

- Führen Sie ComSvcConfig mithilfe der `/list`-Optionen aus, wie im folgenden Beispiel gezeigt:

    ```console
    ComSvcConfig.exe /list
    ```

     Der Befehl listet die derzeit verfügbaren Schnittstellen zusammen mit den entsprechenden Adress- und Bindungsdetails auf, deren Gültigkeitsbereich der lokale Computer ist.

## <a name="list-specific-currently-exposed-interfaces"></a>Auflisten bestimmter aktuell verfügbar gemachter Schnittstellen

- Führen Sie ComSvcConfig mithilfe der `/list`-Optionen aus, wie im folgenden Beispiel gezeigt:

    ```console
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus
    ```

     Der Befehl listet derzeit verfügbare COM+-gehostete Schnittstellen zusammen mit den entsprechenden Adress- und Bindungsdetails für die OnlineStore-COM+-Anwendung auf dem lokalen Computer auf.

## <a name="display-help-for-options"></a>Hilfe zu Optionen anzeigen

- Führen Sie ComSvcConfig mithilfe der /? -Option aus, wie im folgenden Beispiel gezeigt.

    ```console
    ComSvcConfig.exe /?
    ```

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Integration von com+-Anwendungen](integrating-with-com-plus-applications-overview.md)
