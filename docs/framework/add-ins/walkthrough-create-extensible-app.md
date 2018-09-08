---
title: 'Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d2aaeaffaf3abbe1e8efcdb57d40e6ae60f89b5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197586"
---
# <a name="walkthrough-creating-an-extensible-application"></a>Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen
In dieser exemplarischen Vorgehensweise wird beschrieben, wie Sie eine Pipeline für ein Add-in erstellen, die einfachen Taschenrechner Funktionen ausführt. Es wird nicht auf einem realen Szenario veranschaulicht; Stattdessen zeigt es die grundlegende Funktionen einer Pipeline und wie ein Add-In-Dienste für einen Host bereitstellen kann.  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben:  
  
-   Visual Studio-Projektmappe wird erstellt.  
  
-   Erstellen der Pipelineverzeichnisstruktur.  
  
-   Erstellen den Vertrag und Ansichten.  
  
-   Erstellen des Add-In-seitige Adapters an.  
  
-   Den hostseitige Adapter wird erstellt.  
  
-   Erstellen des Hosts.  
  
-   Erstellen das Add-in.  
  
-   Bereitstellen der Pipeline.  
  
-   Die hostanwendung wird ausgeführt.  
  
 Diese Pipeline übergibt nur serialisierbare Typen (<xref:System.Double> und <xref:System.String>), zwischen dem Host und das Add-in. Ein Beispiel, wie Auflistungen von komplexen Datentypen übergeben werden, finden Sie unter [Exemplarische Vorgehensweise: Übergeben von Auflistungen zwischen Hosts und Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).  
  
 Der Vertrag für die Pipeline definiert ein Objektmodell der vier arithmetischen Operationen: hinzufügen, subtrahieren, Multiplizieren und Dividieren. Der Host stellt das Add-in mit einer Formel zum Berechnen, wie z. B. 2 + 2, und gibt Sie das Ergebnis des Add-Ins auf den Host zurück.  
  
 Version 2 von der Rechner-add-in bietet mehr berechnen Möglichkeiten und versionsverwaltung veranschaulicht. Es wird beschrieben, [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host-Änderungen](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese exemplarische Vorgehensweise wird Folgendes benötigt:  
  
-   Visual Studio.  
  
## <a name="creating-a-visual-studio-solution"></a>Erstellen eine Visual Studio-Projektmappe  
 Verwenden Sie eine Lösung in Visual Studio, um die Projekte der Pipelinesegmente enthalten.  
  
#### <a name="to-create-the-pipeline-solution"></a>Zum Erstellen der Pipeline-Lösung  
  
1.  Erstellen Sie in Visual Studio ein neues Projekt namens `Calc1Contract`. Basierend auf den **Klassenbibliothek** Vorlage.  
  
2.  Nennen Sie die Projektmappe `CalculatorV1`.  
  
## <a name="creating-the-pipeline-directory-structure"></a>Erstellen der Pipelineverzeichnisstruktur  
 Das Add-In Modell erfordert, dass die Pipeline Segment Assemblys in einer angegebenen Verzeichnisstruktur platziert werden. Weitere Informationen über die Pipelinestruktur finden Sie unter [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>Zum Erstellen der Pipeline-Verzeichnisstruktur  
  
1.  Erstellen Sie einen Anwendungsordner an einer beliebigen Stelle auf dem Computer.  
  
2.  Erstellen Sie in diesem Ordner die folgende Struktur:  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     Es ist nicht erforderlich, platzieren Sie die Ordnerstruktur für die Pipeline in Ihrem Anwendungsordner; Diese erfolgt hier nur aus praktischen Gründen. Zu gegebener Zeit wird in der exemplarischen Vorgehensweise erläutert, wie den Code ändern, ist die Ordnerstruktur für die Pipeline an einem anderen Speicherort. Finden Sie in den Ausführungen der Pipeline verzeichnisanforderungen in [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
    > [!NOTE]
    >  Die `CalcV2` Ordner wird in dieser exemplarischen Vorgehensweise nicht verwendet; es ist ein Platzhalter für [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host-Änderungen](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="creating-the-contract-and-views"></a>Erstellen des Vertrags und Ansichten  
 Das Vertragssegment für diese Pipeline definiert die `ICalc1Contract` -Schnittstelle, die vier Methoden definiert: `add`, `subtract`, `multiply`, und `divide`.  
  
#### <a name="to-create-the-contract"></a>Um den Vertrag zu erstellen.  
  
1.  In der Visual Studio-Projektmappe, die mit dem Namen `CalculatorV1`öffnen die `Calc1Contract` Projekt.  
  
2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1Contract` Projekt:  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **Klassenbibliothek** Projekte.  
  
4.  In **Projektmappen-Explorer**, fügen Sie dem Projekt ein neues Element mit dem **Schnittstelle** Vorlage. In der **neues Element hinzufügen** klicken Sie im Dialogfeld die Namen der Schnittstelle `ICalc1Contract`.  
  
5.  Fügen Sie Namespaceverweise hinzu, in der Schnittstellendatei <xref:System.AddIn.Contract> und <xref:System.AddIn.Pipeline>.  
  
6.  Verwenden Sie den folgenden Code zum Abschließen dieses Vertragssegment an. Beachten Sie, dass diese Schnittstelle muss die <xref:System.AddIn.Pipeline.AddInContractAttribute> Attribut.  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  Erstellen Sie optional die Visual Studio-Projektmappe. Die Lösung kann nicht ausgeführt werden, bis nach jeder Prozedur stellt sicher, dass jedes Projekt erstellen, aber im letzten Schritt korrigieren.  
  
 Da das Add-In-Ansicht und dem Host angezeigt das Add-in den gleichen Code, besonders in der ersten Version von einem Add-in in der Regel verfügen, können Sie problemlos die Ansichten zur gleichen Zeit erstellen. Sie unterscheiden sich nur ein Aspekt: die View-Add-in erfordert die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut, während die Hostansicht des Add-in-Attribute nicht erfordert.  
  
#### <a name="to-create-the-add-in-view"></a>So erstellen Sie die Ansicht-Add-in  
  
1.  Hinzufügen eines neuen Projekts mit dem Namen `Calc1AddInView` auf die `CalculatorV1` Lösung. Basierend auf den **Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie einen Verweis auf System.AddIn.dll, um die `Calc1AddInView` Projekt.  
  
3.  In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **Klassenbibliothek** projiziert, und fügen Sie dem Projekt ein neues Element mit der **Schnittstelle** Vorlage. In der **neues Element hinzufügen** klicken Sie im Dialogfeld die Namen der Schnittstelle `ICalculator`.  
  
4.  Fügen Sie in der Schnittstellendatei einen Namespaceverweis hinzu <xref:System.AddIn.Pipeline>.  
  
5.  Verwenden Sie den folgenden Code in dieser Ansicht-add-in ausführen. Beachten Sie, dass diese Schnittstelle muss die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut.  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  Erstellen Sie optional die Visual Studio-Projektmappe.  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>Um die Hostansicht des Add-Ins zu erstellen.  
  
1.  Hinzufügen eines neuen Projekts mit dem Namen `Calc1HVA` auf die `CalculatorV1` Lösung. Basierend auf den **Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **Klassenbibliothek** projiziert, und fügen Sie dem Projekt ein neues Element mit der **Schnittstelle** Vorlage. In der **neues Element hinzufügen** klicken Sie im Dialogfeld die Namen der Schnittstelle `ICalculator`.  
  
3.  Verwenden Sie in der Schnittstellendatei den folgenden Code, der die Hostansicht des Add-Ins abgeschlossen.  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-add-in-side-adapter"></a>Den Add-In-seitige Adapter erstellen  
 Dieses Add-In-seitige Adapter besteht aus einem Ansicht-zu-Vertrag-Adapter. Dieses Pipelinesegment konvertiert die Typen aus der Add-In-Ansicht des Vertrags.  
  
 In dieser Pipeline das Add-in bietet einen Dienst an dem Host, und die Typen, die aus dem Add-in auf den Host fließen. Da keine Typen zwischen dem Host und Add-In-fließen, müssen Sie keinen Vertrag-zu-Ansicht-Adapter auf der Seite-Add-in dieser Pipeline aufnehmen.  
  
#### <a name="to-create-the-add-in-side-adapter"></a>Den Add-In-seitige Adapter erstellen  
  
1.  Hinzufügen eines neuen Projekts mit dem Namen `Calc1AddInSideAdapter` auf die `CalculatorV1` Lösung. Basierend auf den **Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1AddInSideAdapter` Projekt:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Fügen Sie Projektverweise auf die Projekte für die benachbarten Pipelinesegmente hinzu:  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  Wählen Sie jeden Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** zu **"false"**. Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"** für die beiden Verweise Projekt.  
  
5.  Benennen Sie die Standardklasse des Projekts `CalculatorViewToContractAddInSideAdapter`.  
  
6.  Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.  
  
7.  Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcAddInViews` und `CalculatorContracts`. (In Visual Basic sind diese Namespaceverweise `Calc1AddInView.CalcAddInViews` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie die Standardnamespaces in Visual Basic-Projekte deaktiviert haben.)  
  
8.  Anwenden der <xref:System.AddIn.Pipeline.AddInAdapterAttribute> -Attribut auf die `CalculatorViewToContractAddInSideAdapter` -Klasse, um den Add-In-seitige Adapter anzugeben.  
  
9. Stellen die `CalculatorViewToContractAddInSideAdapter` Klasse erben <xref:System.AddIn.Pipeline.ContractBase>, die bietet einer Standardimplementierung von der <xref:System.AddIn.Contract.IContract> Schnittstelle, und implementieren Sie die Vertragsschnittstelle für die Pipeline `ICalc1Contract`.  
  
10. Fügen Sie einen öffentlichen Konstruktor, die akzeptiert eine `ICalculator`, speichert es in einem privaten Feld und den Basisklassenkonstruktor aufruft.  
  
11. Das Implementieren von `ICalc1Contract`, rufen Sie einfach die entsprechenden Membern von der `ICalculator` -Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben. Dadurch wird die Ansicht (`ICalculator`) für den Vertrag (`ICalc1Contract`).  
  
     Der folgende Code zeigt die vollständige Add-In-seitige Adapter.  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-host-side-adapter"></a>Den hostseitige Adapter erstellen  
 Diese hostseitiger Adapter besteht aus einem Vertrag-zu-Ansicht-Adapter. Dieses Segment passt sich an den Vertrag, der die Hostansicht des Add-Ins.  
  
 In dieser Pipeline bietet das Add-in einen Dienst auf dem Host und den Fluss von Typen aus dem Add-in auf den Host. Da keine Typen zwischen dem Host und Add-In-fließen, müssen Sie keinen Ansicht-zu-Vertrag-Adapter enthalten.  
  
 Verwenden Sie zum Implementieren der Verwaltung der Lebensdauer einer <xref:System.AddIn.Pipeline.ContractHandle> Lebensdauertoken für den Vertrag anzufügendes Objekt. Sie müssen einen Verweis auf dieses Handle in der Reihenfolge für die Verwaltung der Prozesslebensdauer funktioniert beibehalten. Nachdem das Token angewendet wird, ist keine zusätzliche Programmierung erforderlich, da es sich bei der Add-in-System Objekte freigeben kann, wenn sie nicht mehr verwendet werden und für die Garbagecollection zur Verfügung stellen. Weitere Informationen finden Sie unter [Lebensdauerverwaltung](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
#### <a name="to-create-the-host-side-adapter"></a>Den hostseitige Adapter erstellen  
  
1.  Hinzufügen eines neuen Projekts mit dem Namen `Calc1HostSideAdapter` auf die `CalculatorV1` Lösung. Basierend auf den **Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1HostSideAdapter` Projekt:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Fügen Sie Projektverweise auf die Projekte für die benachbarten Segmente hinzu:  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  Wählen Sie jeden Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** zu **"false"**. Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"** für die beiden Verweise Projekt.  
  
5.  Benennen Sie die Standardklasse des Projekts `CalculatorContractToViewHostSideAdapter`.  
  
6.  Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.  
  
7.  Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcHVAs` und `CalculatorContracts`. (In Visual Basic sind diese Namespaceverweise `Calc1HVA.CalcHVAs` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie die Standardnamespaces in Visual Basic-Projekte deaktiviert haben.)  
  
8.  Anwenden der <xref:System.AddIn.Pipeline.HostAdapterAttribute> -Attribut auf die `CalculatorContractToViewHostSideAdapter` -Klasse, um das Segment der hostseitige Adapter anzugeben.  
  
9. Stellen Sie die `CalculatorContractToViewHostSideAdapter` Klasse implementiert die Schnittstelle, der die Hostansicht des Add-Ins darstellt: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).  
  
10. Fügen Sie einen öffentlichen Konstruktor, die den Vertragstyp der Pipeline akzeptiert `ICalc1Contract`. Der Konstruktor muss den Verweis auf den Vertrag zwischenspeichern. Sie müssen auch erstellen und einen neuen cache <xref:System.AddIn.Pipeline.ContractHandle> für den Vertrag, zum Verwalten der Lebensdauer des Add-Ins.  
  
    > [!IMPORTANT]
    >  Die <xref:System.AddIn.Pipeline.ContractHandle> ist entscheidend für die Verwaltung der Lebensdauer. Wenn Sie nicht behalten Sie einen Verweis auf die <xref:System.AddIn.Pipeline.ContractHandle> -Objekts können Garbagecollection freigegeben wird, und die Pipeline wird heruntergefahren, wenn das Programm nicht erwartet wurden. Dies kann zu Fehlern führen, die schwer zu diagnostizieren, z. B. <xref:System.AppDomainUnloadedException>. Das Herunterfahren ist eine normale Phase im Lebenszyklus einer Pipeline, daher keine Möglichkeit für die Lebensdauer Management Code besteht erkennen, dass diese Bedingung ein Fehler ist.  
  
11. Das Implementieren von `ICalculator`, rufen Sie einfach die entsprechenden Membern von der `ICalc1Contract` -Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben. Dadurch wird der Vertrag (`ICalc1Contract`) an die Ansicht (`ICalculator`).  
  
     Der folgende Code zeigt die abgeschlossenen hostseitiger Adapter.  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-host"></a>Erstellen des Hosts  
 Eine hostanwendung interagiert mit dem Add-in durch die Hostansicht des Add-Ins. Er verwendet die Add-In-Suche und Aktivierung von bereitgestellte Methoden die <xref:System.AddIn.Hosting.AddInStore> und <xref:System.AddIn.Hosting.AddInToken> Klassen die folgenden Schritte ausführen:  
  
-   Aktualisieren Sie den Cache der Pipeline- und Add-in-Informationen.  
  
-   Finden Sie Add-Ins den Hosttyp Ansicht `ICalculator`, unter dem Stammverzeichnis für die angegebene Pipeline.  
  
-   Der Benutzer aufgefordert, geben Sie die-add-in verwenden.  
  
-   Aktivieren Sie das ausgewählte Add-in in einer neuen Anwendungsdomäne mit einer angegebenen Sicherheitsvertrauensebene.  
  
-   Führen Sie die benutzerdefinierte `RunCalculator` -Methode, die das Add-in-Methoden gemäß die Hostansicht des Add-Ins aufruft.  
  
#### <a name="to-create-the-host"></a>Zum Erstellen des Hosts  
  
1.  Hinzufügen eines neuen Projekts mit dem Namen `Calc1Host` auf die `CalculatorV1` Lösung. Basierend auf den **Konsolenanwendung** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die Assembly System.AddIn.dll, um die `Calc1Host` Projekt.  
  
3.  Fügen Sie einen Projektverweis auf die `Calc1HVA` Projekt. Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** zu **"false"**. Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"**.  
  
4.  Benennen Sie die Klassendatei (Modul in Visual Basic) `MathHost1`.  
  
5.  Verwenden Sie in Visual Basic die **Anwendung** Registerkarte die **Projekteigenschaften** Dialogfeld **Startobjekt** zu **Sub Main**.  
  
6.  Fügen Sie in der Klasse oder das Modul-Datei einen Namespaceverweis hinzu <xref:System.AddIn.Hosting>.  
  
7.  Fügen Sie in der Klasse oder das Modul-Datei einen Namespaceverweis für die Hostansicht des Add-Ins: `CalcHVAs`. (In Visual Basic wird dieser Namespaceverweis ist `Calc1HVA.CalcHVAs`, es sei denn, Sie die Standardnamespaces in Visual Basic-Projekte deaktiviert haben.)  
  
8.  In **Projektmappen-Explorer**, wählen Sie die Projektmappe und aus der **Projekt** Menü **Eigenschaften**. In der **Eigenschaftenseiten für Projektmappen** (Dialogfeld), legen die **einzelnes Startprojekt** dieser Hostanwendungsprojekt sein.  
  
9. Verwenden Sie in der Datei Klasse oder das Modul die <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> Methode, um den Cache zu aktualisieren. Verwenden Sie die <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> Methode, um eine Auflistung von Token abrufen und Verwenden der <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> Methode, um ein Add-in zu aktivieren.  
  
     Der folgende Code zeigt die abgeschlossene hostanwendung.  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  Dieser Code wird davon ausgegangen, dass die Pipeline-Ordnerstruktur im Ordner Anwendung befindet. Ändern Sie die Zeile von Code, der festlegt, wenn Sie sie an anderer Stelle befindet, die `addInRoot` -Variablen so, dass die Variable den Pfad zu der Pipelineverzeichnisstruktur enthält.  
  
     Der Code verwendet ein `ChooseCalculator` Methode, die Token aufgeführt und fordert den Benutzer auf ein Add-in auswählen. Die `RunCalculator` Methode fordert den Benutzer einfache mathematische Ausdrücke, analysiert die Ausdrücke mithilfe der `Parser` -Klasse, und zeigt die Ergebnisse zurückgegeben werden, indem Sie das Add-in.  
  
10. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-add-in"></a>Erstellen das Add-In  
 Ein Add-in implementiert die Methoden, die von der Add-In-Ansicht angegeben. Dieses add-in implementiert die `Add`, `Subtract`, `Multiply`, und `Divide` Vorgänge und gibt die Ergebnisse an den Host zurück.  
  
#### <a name="to-create-the-add-in"></a>Um das Add-in zu erstellen.  
  
1.  Hinzufügen eines neuen Projekts mit dem Namen `AddInCalcV1` auf die `CalculatorV1` Lösung. Basierend auf den **Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die System.AddIn.dll-Assembly zum Projekt.  
  
3.  Fügen Sie einen Projektverweis auf die `Calc1AddInView` Projekt. Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften**legen **lokale Kopie** zu **"false"**. Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"** für den Projektverweis.  
  
4.  Benennen Sie die Klasse `AddInCalcV1`.  
  
5.  Fügen Sie in der Klassendatei einen Namespaceverweis hinzu <xref:System.AddIn> und das Add-In-Ansichtssegment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).  
  
6.  Anwenden der <xref:System.AddIn.AddInAttribute> -Attribut auf die `AddInCalcV1` -Klasse, um die Klasse als ein Add-in zu identifizieren.  
  
7.  Stellen Sie die `AddInCalcV1` Klasse implementiert die Schnittstelle, die die Add-In-Ansicht darstellt: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).  
  
8.  Implementieren Sie die Mitglieder der `ICalculator` werden die Ergebnisse der entsprechenden Berechnungen zurückgegeben werden.  
  
     Der folgende Code zeigt die abgeschlossene-add-in.  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="deploying-the-pipeline"></a>Bereitstellen der Pipeline  
 Sie können nun zum Erstellen und Bereitstellen von Add-in-Segmente in der Pipelineverzeichnisstruktur erforderlich.  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>Die Segmente an die Pipeline bereitstellen.  
  
1.  Verwenden Sie für jedes Projekt in der Projektmappe, die **erstellen** Registerkarte **Projekteigenschaften** (die **Kompilieren** Registerkarte in Visual Basic) zum Festlegen des Werts von der **Ausgabepfad**  (die **Buildausgabepfad** in Visual Basic). Wenn Sie den Anwendungsordner Namen `MyApp`, z. B. würden Ihre Projekte erstellen, in den folgenden Ordnern:  
  
    |Projekt|Pfad|  
    |-------------|----------|  
    |AddInCalcV1|MyApp\Pipeline\AddIns\CalcV1|  
    |Calc1AddInSideAdapter|MyApp\Pipeline\AddInSideAdapters|  
    |Calc1AddInView|MyApp\Pipeline\AddInViews|  
    |Calc1Contract|MyApp\Pipeline\Contracts|  
    |Calc1Host|"MyApp"|  
    |Calc1HostSideAdapter|MyApp\Pipeline\HostSideAdapters|  
    |Calc1HVA|"MyApp"|  
  
    > [!NOTE]
    >  Wenn Sie sich entschieden, die Ordnerstruktur für die Pipeline in einem anderen Speicherort als den Anwendungsordner, müssen Sie die Pfade in der Tabelle aufgeführt sind, entsprechend ändern. Finden Sie in den Ausführungen der Pipeline verzeichnisanforderungen in [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
2.  Erstellen Sie die Visual Studio-Projektmappe.  
  
3.  Überprüfen Sie die Anwendung und die Pipeline Verzeichnisse, um sicherzustellen, dass die Assemblys in den richtigen Verzeichnissen kopiert wurden und keine zusätzlichen Kopien der Assemblys in den falschen Ordnern installiert wurden.  
  
    > [!NOTE]
    >  Wenn Sie nicht geändert haben **lokale Kopie** zu **"false"** für die `Calc1AddInView` Projektverweise in der `AddInCalcV1` Projekt Ladeprogramm Kontext Probleme verhindert das Add-in gespeichert werden.  
  
     Informationen zum Bereitstellen von für die Pipeline finden Sie unter [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
## <a name="running-the-host-application"></a>Die Hostanwendung ausführen  
 Sie können nun führen Sie den Host aus, und interagieren mit der Add-in.  
  
#### <a name="to-run-the-host-application"></a>Die hostanwendung ausgeführt.  
  
1.  Klicken Sie an der Eingabeaufforderung, wechseln Sie zum Verzeichnis Anwendung, und führen Sie die hostanwendung, `Calc1Host.exe`.  
  
2.  Der Host alle verfügbare Add-Ins dieses Typs sucht und fordert Sie zum Auswählen eines Add-Ins. Geben Sie **1** für das nur verfügbar, add-in.  
  
3.  Geben Sie eine Formel für den Rechner, z. B. **2 + 2**. Leerzeichen zwischen den Zahlen und den Operator muss vorhanden sein.  
  
4.  Typ **beenden** , und drücken Sie die **EINGABETASTE** Taste, um die Anwendung zu schließen.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität bei geändertem Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [Exemplarische Vorgehensweise: Übergeben von Auflistungen zwischen Hosts und -Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [Anforderungen für die pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [Verträge, Ansichten und Adapter](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [Pipelineentwicklung](../../../docs/framework/add-ins/pipeline-development.md)
