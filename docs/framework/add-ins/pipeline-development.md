---
title: Pipeline-Entwicklung
ms.date: 03/30/2017
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d889b7de4bc766deda9b91877ceefb4aebfc551
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pipeline-development"></a>Pipeline-Entwicklung
Die Add-in-Pipeline ist der Pfad der Pipelinesegmente, die die hostanwendung und seine-Add-in verwenden müssen, um miteinander kommunizieren.  
  
 Die folgende Abbildung zeigt die Kommunikationspipeline und seine Segmente.  
  
 ![Hinzufügen&#45;im Pipeline-Modell. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Add-In-Pipeline  
  
 Die hostanwendung wird an einem Ende der Pipeline, und das Add-in ist am anderen Ende. Beginnend mit beiden Enden, und in die Mitte verschieben, haben die hostanwendung und das Add-in eine abstrakte Basisklasse, die einen Überblick über das Objektmodell definiert, die beide gemeinsam nutzen. Diese Typen (Klassen) bilden zusammen das Anzeigen von Add-in-Pipeline-Segment und der Hostansicht des Add-In-Pipelinesegments. Das Anzeigen von Add-in-Pipeline-Segment enthält oft mehr als eine abstrakte Klasse, aber die Klasse, der das Add-in von erbt als Add-in-Basis bekannt ist.  
  
 Das Add-In-seitiger Adapter Pipeline-Segment und hostseitige Adapter Pipeline Segment konvertieren den Fluss von Typen zwischen ihren Ansichtssegmente der Pipeline und das Vertragssegment der Pipeline. Das zentrale Segment der Pipeline ist ein Vertrag, die abgeleitet ist die <xref:System.AddIn.Contract.IContract> Schnittstelle. Dieser Vertrag definiert die Methoden, die Host-Anwendung und die add-in verwendet werden.  
  
 Wenn Sie den Host und das Add-in in separaten Anwendungsdomänen laden, müssen Sie eine isolationsbegrenzung, die den Bereich der hostanwendung aus dem Bereich des Add-ins trennt. Der Vertrag ist die einzige Assembly, die in den Host und -add-in Anwendungsdomänen geladen wird. Der Host und das Add-in jedes finden Sie nur in ihrer Ansicht eines der Methoden des Dienstvertrags. Aus diesem Grund werden sie durch eine Abstraktionsebene vom Vertrag getrennt.  
  
 Um Pipelinesegmente zu entwickeln, müssen Sie eine Verzeichnisstruktur erstellen, die sie enthält. Weitere Informationen zu den Anforderungen an die Entwicklungsumgebung und Bereich Richtlinien finden Sie unter [Pipelineentwicklung](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
 Die folgende Abbildung zeigt die Typen, die die Pipelinesegmente bilden. Die Namen der Typen in der Abbildung dargestellten wurden willkürlich ausgewählt, jedoch alle Typen außer dem Host und dem Host Anzeigen der Attribute-Add-in erforderlich, damit diese von Methoden gefunden werden können, die einen Informationsspeicher zu erstellen.  
  
 ![Hinzufügen&#45;im Modell mit erforderlichen Attributen für Typen. ] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
Add-in-Pipeline mit Typen  
  
 Die folgende Tabelle beschreibt die Pipelinesegmente für ein Add-in aktivieren. Weitere Informationen zu diesen Segmenten finden Sie unter [Verträge, Ansichten und Adapter](http://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c).  
  
|Pipelinesegment|Beschreibung|  
|----------------------|-----------------|  
|Host|Der Assembly, die eine Instanz ein Add-in erstellt.|  
|Hostansicht des Add-Ins|Stellt die hostanwendung Überblick über die Objekttypen und Methoden zur Kommunikation mit dem Add-in dar. Die Hostansicht ist eine abstrakte Basisklasse oder Schnittstelle.|  
|Hostseitige adapter|Eine Assembly mit einer oder mehreren Klassen, die Methoden in und aus dem Vertrag anpasst.<br /><br /> Diese Pipelinesegment wird identifiziert, mit der <xref:System.AddIn.Pipeline.HostAdapterAttribute> Attribut.<br /><br /> Assemblys mit mehreren Modulen werden nicht unterstützt.|  
|Vertrag|Eine Schnittstelle, die abgeleitet ist die <xref:System.AddIn.Contract.IContract> -Schnittstelle, und dass das Protokoll für die Kommunikation zwischen dem Host und seine Add-in-Typen definiert.<br /><br /> Diese Pipelinesegment wird durch Festlegen von identifiziert die <xref:System.AddIn.Pipeline.AddInContractAttribute> Attribut.|  
|Add-In-seitiger adapter|Eine Assembly mit einer oder mehreren Klassen, die Methoden in und aus dem Vertrag anpasst.<br /><br /> Diese Pipelinesegment wird identifiziert, mit der <xref:System.AddIn.Pipeline.AddInAdapterAttribute> Attribut.<br /><br /> Jede Assembly im Add-In-seitiger Adapterverzeichnis, das einen Typ enthält, ein <xref:System.AddIn.Pipeline.AddInAdapterAttribute> Attribut in die Anwendungsdomäne für das Add-In geladen wird.<br /><br /> Jede Assembly im Add-In-seitiger Verzeichnis wird in einer eigenen Anwendungsdomäne geladen.<br /><br /> Assemblys mit mehreren Modulen werden nicht unterstützt.|  
|Add-In-Ansicht|Eine Assembly, die das Add-in Überblick über die Objekttypen und Methoden, die verwendet werden, um die Kommunikation mit dem Host darstellt. Die Add-In-Ansicht ist eine abstrakte Basisklasse oder Schnittstelle.<br /><br /> Diese Pipelinesegment wird identifiziert, mit der <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut.<br /><br /> Jede Assembly im Verzeichnis AddInViews, die einen Typ enthält, ein <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut in die Anwendungsdomäne für das Add-In geladen wird.|  
|Add-In|Ein instanziierter Typ, der ein Dienst für den Host führt.|  
  
## <a name="pipeline-activation-path"></a>Pipeline-Aktivierungspfad  
 Die folgende Abbildung zeigt die Aktivierung von Typen aus, wenn ein Add-In aktiviert wird. Es zeigt auch die Übergabe von Objekten auf dem Host, z. B. die Ergebnisse einer Berechnung oder eine Auflistung von Objekten. Dies ist das häufigste Szenario.  
  
 ![Hinzufügen&#45;im Modell mit Aktivierungspfad. ] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
Aktivierungspfad aus dem Add-in auf dem host  
  
 Der Aktivierungspfad der Pipeline erfolgt wie folgt aus:  
  
1.  Die hostanwendung aktiviert das Add-in mit der <xref:System.AddIn.Hosting.AddInToken.Activate%2A> Methode.  
  
2.  Die Add-Ins, Add-in-Sicht, Add-In-seitiger Adapter und der Vertragsassemblys werden in das Add-in Anwendungsdomäne geladen.  
  
3.  Eine Instanz von der Add-In-seitiger Adapter wird mithilfe der Add-In-Ansicht erstellt (mit der Klasse identifiziert wird, indem Sie die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut) als Konstruktor. Der Add-In-seitiger Adapter erbt vom Vertrag.  
  
4.  Der Add-In-seitiger-Adapter, die als Vertrag typisiert ist, wird über die Isolationsgrenze (optional) der hostseitige Adapter-Konstruktor übergeben.  
  
5.  Die Hostansicht den Add-Ins, hostseitige Adapter und der Vertragsassemblys werden in der Anwendungsdomäne des Hosts geladen.  
  
6.  Eine Instanz von der hostseitige Adapter wird mit dem Vertrag als Konstruktor erstellt. Der hostseitige Adapter erbt von der Hostansicht des Add-Ins.  
  
7.  Der Host kann das Add-in, das typisiert ist, wie der Host des Add-Ins anzuzeigen, und kann weiterhin ihre Methoden aufrufen.  
  
## <a name="walkthroughs"></a>Exemplarische Vorgehensweisen  
 Es gibt drei exemplarischen Vorgehensweisen, die zum Erstellen von Pipelines mit dem Visual Studio zu beschreiben:  
  
-   [Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     Beschreibt ein Rechner-add-in, die Addition, Subtraktion, Multiplikation und Division Berechnungen für den Host ausführt.  
  
-   [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als die Host-Änderungen](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     Beschreibt ein Rechner-add-in mit erweiterten Berechnungsfunktionen und zum Verwalten der Kompatibilität mit dem ersten Rechner-add-Ins.  
  
-   [Exemplarische Vorgehensweise: Übergeben von Sammlungen zwischen Hosts und -Add-Ins](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     Beschreibt, wie Datensammlungen über die Pipeline, die mit einem Buch Store Szenario zu übergeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Add-In-Pipeline-Szenarien](http://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [Add-Ins und Erweiterbarkeit](../../../docs/framework/add-ins/index.md)
