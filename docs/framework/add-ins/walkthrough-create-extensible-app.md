---
title: 'Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac4b6fc2ae36d848306178f281cceeeb0654ec03
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a>Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen
In dieser exemplarischen Vorgehensweise beschreibt, wie eine Pipeline für ein Add-in zu erstellen, das einfachen Rechnerfunktionen ausführt. Es wird nicht auf einem realen Szenario veranschaulicht; Stattdessen stellt es die grundlegende Funktionalität eines einer Pipeline und wie ein Add-in Dienste für einen Host bereitstellen kann.  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben:  
  
-   Erstellen eine Visual Studio-Projektmappe.  
  
-   Erstellen die Verzeichnisstruktur für die Pipeline an.  
  
-   Der Vertrag und Ansichten werden erstellt.  
  
-   Erstellen die Add-In-seitiger Adapter.  
  
-   Erstellen des hostseitige Adapters an.  
  
-   Erstellen den Host.  
  
-   Erstellen das Add-in.  
  
-   Bereitstellen der Pipeline.  
  
-   Die hostanwendung wird ausgeführt.  
  
 Diese Pipeline übergibt nur serialisierbare Typen (<xref:System.Double> und <xref:System.String>), zwischen dem Host und das Add-in. Ein Beispiel, das zeigt, wie Auflistungen von komplexen Datentypen übergeben werden, finden Sie unter [Exemplarische Vorgehensweise: Übergeben von Sammlungen zwischen Hosts und -Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).  
  
 Der Vertrag für diese Pipeline definiert ein Objektmodell aus vier arithmetischen Operationen: hinzufügen, subtrahieren, Multiplizieren und Dividieren. Der Host stellt das Add-in mit einer Formel zum Berechnen, wie z. B. 2 + 2, und das Add-in gibt das Ergebnis an den Host zurück.  
  
 Version 2 des Rechner-add-Ins bietet mehr berechnen Möglichkeiten und versionsverwaltung veranschaulicht. Es wird beschrieben, [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host Änderungen](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese exemplarische Vorgehensweise wird Folgendes benötigt:  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]  
  
## <a name="creating-a-visual-studio-solution"></a>Erstellen einer Visual Studio-Projektmappe  
 Verwenden Sie eine Projektmappe in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] , die Projekte der Pipelinesegmente enthalten.  
  
#### <a name="to-create-the-pipeline-solution"></a>Zum Erstellen der Pipeline-Lösung  
  
1.  In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], erstellen Sie ein neues Projekt mit dem Namen `Calc1Contract`. Basierend auf den **-Klassenbibliothek** Vorlage.  
  
2.  Nennen Sie die Projektmappe `CalculatorV1`.  
  
## <a name="creating-the-pipeline-directory-structure"></a>Erstellen der Pipelineverzeichnisstruktur  
 Das Add-In Modell erfordert, dass die Pipeline Segment Assemblys in einer angegebenen Verzeichnisstruktur platziert werden. Weitere Informationen über die Pipelinestruktur finden Sie unter [Pipelineentwicklung](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>Zum Erstellen der Pipeline-Verzeichnisstruktur  
  
1.  Erstellen Sie einen Anwendungsordner an einer beliebigen Stelle auf Ihrem Computer.  
  
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
  
     Es ist nicht erforderlich, platzieren die Ordnerstruktur für die Pipeline in Ihrem Anwendungsordner; Dies erfolgt hier nur zur Vereinfachung für. Den entsprechenden Schritt wird die exemplarischen Vorgehensweise erläutert, wie den Code ändern, wenn die Ordnerstruktur für die Pipeline an einem anderen Speicherort. Finden Sie in den Ausführungen des Pipeline-Directory-Anforderungen in [Pipelineentwicklung](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
    > [!NOTE]
    >  Die `CalcV2` Ordner wird in dieser exemplarischen Vorgehensweise nicht verwendet; es ist ein Platzhalter für [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host Änderungen](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="creating-the-contract-and-views"></a>Der Vertrag und Ansichten werden erstellt  
 Das Vertragssegment für diese Pipeline definiert die `ICalc1Contract` -Schnittstelle, die vier Methoden definiert: `add`, `subtract`, `multiply`, und `divide`.  
  
#### <a name="to-create-the-contract"></a>Um den Vertrag zu erstellen.  
  
1.  In der Visual Studio-Projektmappe mit dem Namen `CalculatorV1`öffnen die `Calc1Contract` Projekt.  
  
2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1Contract` Projekt:  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **-Klassenbibliothek** Projekte.  
  
4.  In **Projektmappen-Explorer**, Hinzufügen eines neuen Elements zum Projekt mit der **Schnittstelle** Vorlage. In der **neues Element hinzufügen** (Dialogfeld), Name der Schnittstelle `ICalc1Contract`.  
  
5.  Fügen Sie Namespaceverweise hinzu, in der Schnittstellendatei <xref:System.AddIn.Contract> und <xref:System.AddIn.Pipeline>.  
  
6.  Verwenden Sie den folgenden Code, um dieses Vertragssegment abzuschließen. Beachten Sie, dass diese Schnittstelle muss das <xref:System.AddIn.Pipeline.AddInContractAttribute> Attribut.  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  Erstellen Sie optional die Visual Studio-Projektmappe. Die Lösung kann nicht ausgeführt werden, bis nach jeder Prozedur stellt sicher, dass jedes Projekt erstellen, aber mit dem abschließenden Verfahren korrigieren.  
  
 Da die Add-In-Ansicht und der Host des anzeigen das Add-in den gleichen Code, besonders in der ersten Version von einem Add-in in der Regel haben, können Sie problemlos Ansichten zur gleichen Zeit erstellt. Sie unterscheiden sich nur eine einstufige: die View-Add-in erfordert die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut, während die Hostansicht des Add-Ins keine Attribute erforderlich ist.  
  
#### <a name="to-create-the-add-in-view"></a>So erstellen Sie die Add-In-Ansicht  
  
1.  Fügen Sie ein neues Projekt mit dem Namen `Calc1AddInView` auf die `CalculatorV1` Lösung. Basierend auf den **-Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie einen Verweis auf System.AddIn.dll auf die `Calc1AddInView` Projekt.  
  
3.  In **Projektmappen-Explorer**, schließen Sie die Standardklasse, das hinzugefügt wird, neu **-Klassenbibliothek** -Projekten und Hinzufügen eines neuen Elements zum Projekt mit der **Schnittstelle** Vorlage. In der **neues Element hinzufügen** (Dialogfeld), Name der Schnittstelle `ICalculator`.  
  
4.  Fügen Sie in der Schnittstellendatei einen Namespaceverweis auf <xref:System.AddIn.Pipeline>.  
  
5.  Verwenden Sie den folgenden Code, um diese Add-In-Ansicht abzuschließen. Beachten Sie, dass diese Schnittstelle muss das <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut.  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  Erstellen Sie optional die Visual Studio-Projektmappe.  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>So erstellen die Hostansicht des Add-Ins  
  
1.  Fügen Sie ein neues Projekt mit dem Namen `Calc1HVA` auf die `CalculatorV1` Lösung. Basierend auf den **-Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, schließen Sie die Standardklasse, das hinzugefügt wird, neu **-Klassenbibliothek** -Projekten und Hinzufügen eines neuen Elements zum Projekt mit der **Schnittstelle** Vorlage. In der **neues Element hinzufügen** (Dialogfeld), Name der Schnittstelle `ICalculator`.  
  
3.  Verwenden Sie den folgenden Code in der Schnittstellendatei zum Abschließen der Hostansicht des Add-Ins.  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-add-in-side-adapter"></a>Erstellen die Add-In-seitiger Adapter  
 Dieses Add-In-seitiger Adapter besteht aus einem Ansicht-zu-Vertrag-Adapter. Dieses Pipelinesegment konvertiert die Typen aus der Add-In-Ansicht mit dem Vertrag.  
  
 In dieser Pipeline das Add-in bietet einen Dienst auf dem Host, und die Typen, die aus dem Add-in auf dem Host fließen. Da keine Typen vom Host für die Add-in übergeben, müssen Sie keinen Vertrag-zu-Ansicht-Adapter auf der Add-in-Seite dieser Pipeline aufnehmen.  
  
#### <a name="to-create-the-add-in-side-adapter"></a>Den Add-In-seitiger Adapter erstellen  
  
1.  Fügen Sie ein neues Projekt mit dem Namen `Calc1AddInSideAdapter` auf die `CalculatorV1` Lösung. Basierend auf den **-Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1AddInSideAdapter` Projekt:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Fügen Sie Projektverweise die Projekte für die benachbarten Pipelinesegmente hinzu:  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  Wählen Sie jede Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** auf **"false"**. In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"** für die beiden Verweise Projekt.  
  
5.  Benennen Sie das Projekt Standardklasse `CalculatorViewToContractAddInSideAdapter`.  
  
6.  Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.  
  
7.  Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcAddInViews` und `CalculatorContracts`. (In Visual Basic werden diese Namespaceverweise `Calc1AddInView.CalcAddInViews` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie in Visual Basic-Projekte die Standardnamespaces deaktiviert haben.)  
  
8.  Anwenden der <xref:System.AddIn.Pipeline.AddInAdapterAttribute> -Attribut auf die `CalculatorViewToContractAddInSideAdapter` -Klasse, um es als die Add-In-seitiger Adapter zu identifizieren.  
  
9. Stellen Sie die `CalculatorViewToContractAddInSideAdapter` Klasse erben <xref:System.AddIn.Pipeline.ContractBase>, stellt eine Standardimplementierung von der <xref:System.AddIn.Contract.IContract> Schnittstelle, und implementieren Sie die Vertragsschnittstelle für die Pipeline `ICalc1Contract`.  
  
10. Fügen Sie einen öffentlichen Konstruktor, das akzeptiert ein `ICalculator`, speichert es in einem privaten Feld und der Basisklassenkonstruktor aufruft.  
  
11. Das Implementieren von `ICalc1Contract`, rufen Sie einfach die entsprechenden Mitgliedern von der `ICalculator` Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben. Dadurch wird die Ansicht (`ICalculator`) mit dem Vertrag (`ICalc1Contract`).  
  
     Der folgende Code zeigt die vollständige Add-In-seitiger Adapter.  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-host-side-adapter"></a>Den hostseitige Adapter erstellen  
 Dieser hostseitige Adapter besteht aus einem Vertrag-zu-Ansicht-Adapter. Dieses Segment wird der Vertrag, der die Hostansicht des Add-Ins.  
  
 In dieser Pipeline bietet das Add-in einen Dienst auf dem Host und den Fluss von Typen aus dem Add-in auf dem Host. Da keine Typen vom Host für die Add-in übergeben, müssen Sie keinen Ansicht zu Vertrag-Adapter enthalten.  
  
 Verwenden Sie zum Implementieren der Verwaltung der Lebensdauer einer <xref:System.AddIn.Pipeline.ContractHandle> ein Lebensdauertoken der Vertrag anzufügende Objekt. Sie müssen einen Verweis auf dieses Handle in der Reihenfolge für die Verwaltung der Objektlebensdauer zu behalten. Nachdem das Token angewendet wird, ist keine zusätzliche Programmierung erforderlich, da das Add-in-System Objekte freigeben kann, wenn sie nicht mehr verwendet werden und für die Garbagecollection zur Verfügung stellen. Weitere Informationen finden Sie unter [Verwaltung der Lebensdauer](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
#### <a name="to-create-the-host-side-adapter"></a>So erstellen Sie die hostseitige adapter  
  
1.  Fügen Sie ein neues Projekt mit dem Namen `Calc1HostSideAdapter` auf die `CalculatorV1` Lösung. Basierend auf den **-Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1HostSideAdapter` Projekt:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Fügen Sie Projektverweise für die Projekte für die benachbarten Segmente hinzu:  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  Wählen Sie jede Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** auf **"false"**. In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"** für die beiden Verweise Projekt.  
  
5.  Benennen Sie das Projekt Standardklasse `CalculatorContractToViewHostSideAdapter`.  
  
6.  Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.  
  
7.  Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcHVAs` und `CalculatorContracts`. (In Visual Basic werden diese Namespaceverweise `Calc1HVA.CalcHVAs` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie in Visual Basic-Projekte die Standardnamespaces deaktiviert haben.)  
  
8.  Anwenden der <xref:System.AddIn.Pipeline.HostAdapterAttribute> -Attribut auf die `CalculatorContractToViewHostSideAdapter` -Klasse, um es als das Adaptersegment hostseitige zu identifizieren.  
  
9. Stellen Sie die `CalculatorContractToViewHostSideAdapter` Klasse implementiert die Schnittstelle, die die Hostansicht des Add-Ins darstellt: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).  
  
10. Fügen Sie einen öffentlichen Konstruktor, der den Typ des Pipeline-Vertrags akzeptiert `ICalc1Contract`. Der Konstruktor, muss den Verweis auf den Vertrag zwischenspeichern. Sie müssen auch erstellen und einen neuen cache <xref:System.AddIn.Pipeline.ContractHandle> für den Vertrag, zum Verwalten der Lebensdauer des Add-Ins.  
  
    > [!IMPORTANT]
    >  Die <xref:System.AddIn.Pipeline.ContractHandle> für die Verwaltung der Lebensdauer von entscheidender Bedeutung ist. Wenn Sie ein Failover zu einem Verweis auf die <xref:System.AddIn.Pipeline.ContractHandle> -Objekts können Garbagecollection freigegeben, und die Pipeline wird heruntergefahren, wenn das Programm nicht erwartet. Dies kann zu Fehlern, die schwer zu diagnostizieren, wie z. B. sind <xref:System.AppDomainUnloadedException>. Shutdown ist eine normale Phase während der Lebensdauer einer Pipeline, daher keine Möglichkeit für die Lebensdauer Management Code besteht erkennen, dass diese Bedingung ein Fehler ist.  
  
11. Das Implementieren von `ICalculator`, rufen Sie einfach die entsprechenden Mitgliedern von der `ICalc1Contract` Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben. Dadurch wird der Vertrag (`ICalc1Contract`) zur Ansicht (`ICalculator`).  
  
     Der folgende Code zeigt die vollständige hostseitige Adapter.  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-host"></a>Erstellen des Hosts  
 Eine hostanwendung interagiert mit dem Add-in über die Hostansicht des Add-Ins. Add-In-Suche und Aktivierung von bereitgestellte Methoden verwendet die <xref:System.AddIn.Hosting.AddInStore> und <xref:System.AddIn.Hosting.AddInToken> Klassen, die folgenden Aktionen ausführen:  
  
-   Aktualisieren des Caches der Pipeline und Add-in-Informationen an.  
  
-   Suchen-add-ins von den Hosttyp Ansicht `ICalculator`, unter dem Stammverzeichnis des angegebenen Pipeline.  
  
-   Der Benutzer aufgefordert, geben Sie die add-in verwenden.  
  
-   Aktivieren Sie die ausgewählten Add-Ins in eine neue Anwendungsdomäne mit der angegebenen Vertrauenswürdigkeit Sicherheitsstufe.  
  
-   Führen Sie das benutzerdefinierte `RunCalculator` -Methode, die das Add-in Methoden gemäß der Hostansicht des Add-Ins aufruft.  
  
#### <a name="to-create-the-host"></a>Zum Erstellen des Hosts  
  
1.  Fügen Sie ein neues Projekt mit dem Namen `Calc1Host` auf die `CalculatorV1` Lösung. Basierend auf den **Konsolenanwendung** Vorlage.  
  
2.  In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die System.AddIn.dll-Assembly, auf die `Calc1Host` Projekt.  
  
3.  Fügen Sie einen Projektverweis auf die `Calc1HVA` Projekt. Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** auf **"false"**. In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"**.  
  
4.  Benennen Sie die Klassendatei (Modul in Visual Basic) `MathHost1`.  
  
5.  Verwenden Sie in Visual Basic die **Anwendung** auf der Registerkarte die **Projekteigenschaften** Dialogfeld **Startobjekt** auf **Sub Main**.  
  
6.  Fügen Sie in der Klasse oder des Moduls-Datei einen Namespaceverweis auf <xref:System.AddIn.Hosting>.  
  
7.  Fügen Sie in der Klasse oder des Moduls-Datei einen Namespaceverweis für die Hostansicht des Add-Ins: `CalcHVAs`. (In Visual Basic wird diese Namespaceverweis `Calc1HVA.CalcHVAs`, es sei denn, Sie in Visual Basic-Projekte die Standardnamespaces deaktiviert haben.)  
  
8.  In **Projektmappen-Explorer**, wählen Sie die Projektmappe und aus der **Projekt** im Menü **Eigenschaften**. In der **-Eigenschaftenseiten** (Dialogfeld), legen die **einzelnes Startprojekt** dieses Hostanwendungsprojekt sein.  
  
9. Verwenden Sie in der Datei Klasse oder das Modul die <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> Methode, um den Cache aktualisieren. Verwenden Sie die <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> Methode zum Abrufen einer Auflistung der Token und zum Verwenden der <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> Methode, um ein Add-in aktivieren.  
  
     Der folgende Code zeigt den abgeschlossenen hostanwendung.  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  Mit diesem Code wird davon ausgegangen, dass die Ordnerstruktur für die Pipeline im Ordner Anwendung befindet. Ändern Sie die Zeile des Codes, der festlegt, an anderer Stelle befindet, die `addInRoot` -Variablen so, dass die Variable den Pfad zur Pipelineverzeichnisstruktur enthält.  
  
     Der Code verwendet eine `ChooseCalculator` Methode, um die Token aufzulisten und fordert den Benutzer auf ein Add-in auswählen. Die `RunCalculator` Methode fordert den Benutzer einfache mathematische Ausdrücke, analysiert die Ausdrücke mithilfe der `Parser` -Klasse, und zeigt die Ergebnisse zurückgegeben werden, indem Sie das Add-in.  
  
10. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="creating-the-add-in"></a>Erstellen das Add-In  
 Ein Add-In implementiert die Methoden, die von der Add-in-Sicht angegeben. Dieses Add-In implementiert die `Add`, `Subtract`, `Multiply`, und `Divide` Vorgänge und gibt die Ergebnisse an den Host zurück.  
  
#### <a name="to-create-the-add-in"></a>So erstellen das Add-in  
  
1.  Fügen Sie ein neues Projekt mit dem Namen `AddInCalcV1` auf die `CalculatorV1` Lösung. Basierend auf den **-Klassenbibliothek** Vorlage.  
  
2.  In **Projektmappen-Explorer**, dem Projekt einen Verweis auf die System.AddIn.dll-Assembly hinzugefügt.  
  
3.  Fügen Sie einen Projektverweis auf die `Calc1AddInView` Projekt. Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften**legen **lokale Kopie** auf **"false"**. In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"** für den Projektverweis.  
  
4.  Benennen Sie die Klasse `AddInCalcV1`.  
  
5.  Fügen Sie in der Klassendatei einen Namespaceverweis auf <xref:System.AddIn> und das Anzeigen von Add-in-Segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).  
  
6.  Anwenden der <xref:System.AddIn.AddInAttribute> -Attribut auf die `AddInCalcV1` -Klasse, um die Klasse als ein Add-in zu identifizieren.  
  
7.  Stellen Sie die `AddInCalcV1` Klasse implementiert die Schnittstelle, die die Add-In-Ansicht darstellt: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).  
  
8.  Implementieren Sie die Mitglieder der `ICalculator` durch die Ergebnisse von den entsprechenden Berechnungen zurückgeben.  
  
     Der folgende Code zeigt den abgeschlossenen-add-in.  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. Erstellen Sie optional die Visual Studio-Projektmappe.  
  
## <a name="deploying-the-pipeline"></a>Bereitstellen der Pipeline  
 Sie können nun zum Erstellen und Bereitstellen der Add-in-Segmente an der Pipelineverzeichnisstruktur erforderlich.  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>Die Segmente in der Pipeline bereitstellen  
  
1.  Verwenden Sie für jedes Projekt in der Projektmappe, die **erstellen** Registerkarte **Projekteigenschaften** (die **Kompilieren** Registerkarte in Visual Basic) zum Festlegen des Werts von der **Ausgabepfad**  (die **Buildausgabepfad** in Visual Basic). Wenn Sie mit dem Namen Anwendungsordner `MyApp`, z. B. würde Ihre Projekte erstellen, in den folgenden Ordnern:  
  
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
    >  Wenn Sie sich entschieden, die Ordnerstruktur für die Pipeline in einem anderen Speicherort als den Anwendungsordner, müssen Sie die Pfade in der Tabelle aufgeführt sind, entsprechend ändern. Finden Sie in den Ausführungen des Pipeline-Directory-Anforderungen in [Pipelineentwicklung](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
2.  Erstellen Sie die Visual Studio-Projektmappe.  
  
3.  Überprüfen Sie die Anwendung und die Pipeline Verzeichnisse, um sicherzustellen, dass die Assemblys in den richtigen Verzeichnissen kopiert wurden und keine zusätzlichen Kopien der Assemblys in der falschen Ordnern installiert wurden.  
  
    > [!NOTE]
    >  Wenn Sie nicht geändert hat **lokale Kopie** auf **"false"** für die `Calc1AddInView` Projektverweise in der `AddInCalcV1` Projekt Ladeprogramm Kontext Probleme verhindert das Add-in befindlich.  
  
     Informationen zur Bereitstellung in der Pipeline finden Sie unter [Pipelineentwicklung](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
## <a name="running-the-host-application"></a>Ausführen der Hostanwendung  
 Sie können nun den Host ausführen und interagieren mit dem Add-in.  
  
#### <a name="to-run-the-host-application"></a>Zum Ausführen der hostanwendung  
  
1.  An der Eingabeaufforderung, wechseln Sie zum Verzeichnis Anwendung, und führen Sie die hostanwendung `Calc1Host.exe`.  
  
2.  Der Host sucht alle verfügbaren Add-Ins dieses Typs und fordert Sie auf ein Add-in auszuwählen. Geben Sie **1** für die einzige verfügbare Add-in.  
  
3.  Geben Sie eine Formel für den Rechner, z. B. **2 + 2**. Leerzeichen zwischen den Zahlen und der Operator muss vorhanden sein.  
  
4.  Typ **beenden** , und drücken Sie die **EINGABETASTE** Taste, um die Anwendung zu schließen.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als die Host-Änderungen](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [Exemplarische Vorgehensweise: Übergeben von Sammlungen zwischen Hosts und -Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [Pipelineentwicklung](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [Verträge, Ansichten und Adapter](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [Pipelineentwicklung](../../../docs/framework/add-ins/pipeline-development.md)
