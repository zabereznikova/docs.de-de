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
ms.openlocfilehash: f981d667f3cbf35ab010ac5bd26a9ecd5c2aae11
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151342"
---
# <a name="pipeline-development"></a>Pipeline-Entwicklung
Die Add-in-Pipeline ist der Pfad der Pipelinesegmente, die die hostanwendung und der Add-in verwenden müssen, um miteinander zu kommunizieren.  
  
 Die folgende Abbildung zeigt die Kommunikationspipeline und seine Segmente.  
  
 ![Hinzufügen&#45;im pipelinemodell. ](../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Add-In-Pipeline  
  
 Die hostanwendung an einem Ende der Pipeline ist und das Add-in ist am anderen Ende. Beginnend mit beiden Enden, und verschieben in die Mitte, haben sowohl die Host-Anwendung als auch das Add-in eine abstrakte Basisklasse, die einen Überblick über das Objektmodell definiert, die beide gemeinsam nutzen. Diese Typen (Klassen), bilden des Add-in-Ansichtspipelinesegments und die Hostansicht des Add-in-Pipeline-Segments ab. Das Add-In-Ansichtspipelinesegment enthält oft mehr als eine abstrakte Klasse, aber die Klasse, der das Add-in von erbt als Basis-Add-in bekannt ist.  
  
 Die Add-In-seitigen Adapterpipelinesegments und der hostseitige Adapter Pipeline konvertieren den Fluss von Datentypen zwischen ihrer Ansichtssegmente der Pipeline und des Vertragspipelinesegments. Das zentrale Segment der Pipeline ist, einen Vertrag, der von abgeleitet ist die <xref:System.AddIn.Contract.IContract> Schnittstelle. Dieser Vertrag definiert die Methoden, die die hostanwendung und der add-in verwendet werden.  
  
 Wenn Sie dem Host und das Add-in in getrennte Anwendungsdomänen laden, müssen Sie eine isolationsbegrenzung, die den Rahmen der hostanwendung aus dem Bereich, der das Add-in trennt. Der Vertrag ist die einzige Assembly, die in den Host und Add-in-Anwendungsdomänen geladen wird. Der Host und das Add-in jedes beziehen sich nur für die Darstellung der der Contract-Methoden. Aus diesem Grund werden sie durch eine Abstraktionsebene vom Vertrag getrennt.  
  
 Um Pipelinesegmente entwickeln zu können, müssen Sie eine Verzeichnisstruktur erstellen, die sie enthält. Weitere Informationen zu den Anforderungen für die Entwicklung und Bereichs-Richtlinien finden Sie unter [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
 Die folgende Abbildung zeigt die Typen, die der Pipelinesegmente bilden. Die Namen der Typen in der Abbildung dargestellten wurden willkürlich ausgewählt, aber alle Typen außer dem Host und dem Host-Add-ins erfordern Attribute anzeigen, damit diese durch Methoden gefunden werden können, die einen Informationsspeicher zu erstellen.  
  
 ![Hinzufügen&#45;im Modell mit erforderlichen Attributen für Typen. ](../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
Add-in-Pipeline mit Typen  
  
 Die folgende Tabelle beschreibt der Pipelinesegmente für ein Add-in aktivieren. Weitere Informationen zu diesen Segmenten finden Sie unter [Verträge, Ansichten und Adapter](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c).  
  
|Pipelinesegmente|Beschreibung|  
|----------------------|-----------------|  
|Host|Der Assembly, die eine Instanz von einem Add-in erstellt.|  
|Hostansicht des Add-Ins|Stellt die hostanwendung die Objekttypen und Methoden, die zur Kommunikation mit dem Add-In-Ansicht dar. Die hostanwendung die Hostansicht ist eine abstrakte Basisklasse oder Schnittstelle.|  
|Hostseitiger adapter|Eine Assembly mit der eine oder mehrere Klassen, die Methoden zum und vom Vertrag anpasst.<br /><br /> Dieses Pipelinesegment wird mit identifiziert die <xref:System.AddIn.Pipeline.HostAdapterAttribute> Attribut.<br /><br /> Assemblys mit mehreren Modulen werden nicht unterstützt.|  
|Vertrag|Eine Schnittstelle, die von abgeleitet ist die <xref:System.AddIn.Contract.IContract> Schnittstelle zudem wird festgelegt, das Protokoll für die Kommunikation von Typen, die zwischen dem Host und seine-add-in.<br /><br /> Dieses Pipelinesegment wird durch Festlegen von identifiziert die <xref:System.AddIn.Pipeline.AddInContractAttribute> Attribut.|  
|Add-In-seitige adapter|Eine Assembly mit der eine oder mehrere Klassen, die Methoden zum und vom Vertrag anpasst.<br /><br /> Dieses Pipelinesegment wird mit identifiziert die <xref:System.AddIn.Pipeline.AddInAdapterAttribute> Attribut.<br /><br /> Jede Assembly im Add-In-seitige Adapterverzeichnis, das einen Typ enthält, die eine <xref:System.AddIn.Pipeline.AddInAdapterAttribute> Attribut in das Add-in die Anwendungsdomäne geladen wird.<br /><br /> Jede Assembly im Add-In-seitige Verzeichnis wird in seiner eigenen Anwendungsdomäne geladen.<br /><br /> Assemblys mit mehreren Modulen werden nicht unterstützt.|  
|Add-In-Ansicht|Eine Assembly, die das Add-In-Ansicht der Objekte des Typs und Methoden, die verwendet werden, für die Kommunikation mit dem Host darstellt. Die Add-In Ansicht ist eine abstrakte Basisklasse oder Schnittstelle.<br /><br /> Dieses Pipelinesegment wird mit identifiziert die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut.<br /><br /> Jede Assembly im Verzeichnis AddInViews, das einen Typ enthält, die eine <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut in das Add-in die Anwendungsdomäne geladen wird.|  
|Add-In|Einen instanziierten Typ, der einen Dienst für den Host ausführt.|  
  
## <a name="pipeline-activation-path"></a>Pipeline-Aktivierungspfad  
 Die folgende Abbildung zeigt die Aktivierung von Typen aus, wenn ein Add-in aktiviert ist. Es zeigt auch die Übergabe von Objekten an dem Host, z. B. die Ergebnisse einer Berechnung oder eine Auflistung von Objekten an. Dies ist das typische Szenario.  
  
 ![Hinzufügen&#45;im Modell mit Aktivierungspfad. ](../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
Aktivierungspfad aus dem Add-in auf dem host  
  
 Der Aktivierungspfad der Pipeline erfolgt folgendermaßen:  
  
1.  Die hostanwendung aktiviert das Add-in mit der <xref:System.AddIn.Hosting.AddInToken.Activate%2A> Methode.  
  
2.  Der Add-Ins, Add-In-Ansicht, Add-In-seitige Adapter und der Vertragsassemblys werden in das Add-in die Anwendungsdomäne geladen.  
  
3.  Eine Instanz des Add-In-seitigen Adapters wird erstellt, mit der View-Add-in (mit der Klasse, die von identifiziert die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut) als Konstruktor. Der Add-In-seitige Adapter erbt vom Vertrag.  
  
4.  Die Add-In-seitige Adapter, die als Vertrag typisiert ist, wird über die isolationsbegrenzung für (optional) an der hostseitige Adapter-Konstruktor übergeben.  
  
5.  Die Hostansicht des der Add-Ins, hostseitige Adapter und die Vertragsassemblys sind in der Anwendungsdomäne des Hosts geladen werden.  
  
6.  Eine Instanz von der hostseitige Adapter wird mit dem Vertrag als seinem Konstruktor erstellt. Der hostseitige Adapter erbt von die Hostansicht des Add-Ins ab.  
  
7.  Der Host kann die Add-in, das eingegeben wurde, wie der Host das Add-In-Ansicht und kann weiterhin seine Methoden aufrufen.  
  
## <a name="walkthroughs"></a>Exemplarische Vorgehensweisen  
 Es gibt drei exemplarischen Vorgehensweisen, die beschreiben, wie Sie Pipelines mithilfe von Visual Studio erstellen:  
  
-   [Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     Beschreibt ein Rechner-add-in, die Addition, Subtraktion, Multiplikation und Division Berechnungen für den Host ausführt.  
  
-   [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität bei geändertem Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     Beschreibt ein Rechner-add-in mit erweiterten Berechnungsfunktionen und wie Sie die Kompatibilität mit der ersten Rechner-add-Ins zu gewährleisten.  
  
-   [Exemplarische Vorgehensweise: Übergeben von Auflistungen zwischen Hosts und -Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     Beschreibt, wie datenauflistungen über die Pipeline basierend auf einem Buch Store übergeben.  
  
## <a name="see-also"></a>Siehe auch  
- [Add-In-Pipeline-Szenarios](https://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
- [Add-Ins und Erweiterbarkeit](../../../docs/framework/add-ins/index.md)
