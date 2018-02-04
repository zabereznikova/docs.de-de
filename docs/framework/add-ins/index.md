---
title: Add-Ins und Erweiterbarkeit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d288d321063512f91ad94b417bb1a6bf38c9ef9
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="add-ins-and-extensibility"></a>Add-Ins und Erweiterbarkeit
<a name="top"></a> Add-Ins stellen erweiterte Funktionen oder Dienste für eine Hostanwendung bereit. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] stellt ein Programmiermodell bereit, mit dem Entwickler Add-Ins entwickeln und in ihrer Hostanwendung aktivieren können. Zu diesem Zweck erstellt das Modell eine Kommunikationspipeline zwischen dem Host und dem Add-In. Das Modell wird implementiert, indem die Typen in den Namespaces <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>und <xref:System.AddIn.Contract> verwendet werden.  
  
 Diese Übersicht enthält folgende Abschnitte:  
  
-   [Add-In-Modell](#addin_model)  
  
-   [Unterscheiden zwischen Add-Ins und Hosts](#distinguishing_between_addins_and_hosts)  
  
-   [Verwandte Themen](#related_topics)  
  
-   [Verweis](#reference)  
  
> [!NOTE]
>  Zusätzlichen Beispielcode und Customer Technology Previews von Tools zum Erstellen von Add-In-Pipelines finden Sie auf der [Managed Extensibility and Add-In Framework-Website auf CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a>Add-In-Modell  
 Das Add-In-Modell besteht aus einer Reihe von Segmenten, die die Add-in-Pipeline (wird auch als Kommunikationspipeline bezeichnet) bilden, die für die gesamte Kommunikation zwischen dem Add-In und dem Host verantwortlich ist. Die Pipeline ist ein symmetrisches Kommunikationsmodell von Segmenten, die Daten zwischen einem Add-In und dessen Host austauschen. Durch die Entwicklung dieser Segmente zwischen dem Host und dem Add-In werden die erforderlichen Abstraktionsebenen bereitgestellt, die die Versionsverwaltung und Isolation des Add-Ins unterstützen.  
  
 In der folgenden Abbildung ist die Pipeline dargestellt.  
  
 ![Hinzufügen &#45; im Pipeline-Modell. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Add-In-Pipeline  
  
 Die Assemblys für diese Segmente müssen sich nicht in derselben Anwendungsdomäne befinden. Sie können ein Add-In in seine eigene neue Anwendungsdomäne, in eine vorhandene Anwendungsdomäne oder sogar in die Anwendungsdomäne des Hosts laden. Sie können mehrere Add-Ins in dieselbe Anwendungsdomäne laden. Dadurch können die Add-Ins Ressourcen und Sicherheitskontexte gemeinsam nutzen.  
  
 Das Add-In-Modell unterstützt und empfiehlt eine optionale Grenze zwischen dem Host und dem Add-In, die als Isolationsgrenze ( oder auch als Remotegrenze) bezeichnet wird. Diese Grenze kann eine Anwendungsdomänen- oder Prozessgrenze sein.  
  
 Das Vertragssegment in der Mitte der Pipeline wird in die Anwendungsdomäne des Hosts und in die Anwendungsdomäne des Add-Ins geladen. Der Vertrag definiert die virtuellen Methoden, mit denen der Host und das Add-In Typen austauschen.  
  
 Um die Isolationsgrenze überwinden zu können, muss es sich bei den Typen um Verträge oder serialisierbare Typen handeln. Typen, die weder Verträge noch serialisierbare Typen sind, müssen von den Adaptersegmenten in der Pipeline in Verträge konvertiert werden.  
  
 Die Ansichtssegmente der Pipeline sind abstrakte Basisklassen oder Schnittstellen, die dem Host und dem Add-In eine Ansicht der gemeinsam genutzten Methoden (gemäß der Vertragsdefinition) zur Verfügung stellen.  
  
 Weitere Informationen zum Entwickeln von Pipelinesegmenten finden Sie unter [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).  
  
 In den folgenden Abschnitten werden die Funktionen des Add-In-Modells beschrieben.  
  
### <a name="independent-versioning"></a>Unabhängige Versionsverwaltung  
 Das Add-In-Modell ermöglicht Hosts und Add-Ins eine unabhängige Versionsverwaltung. Dadurch ermöglicht das Add-In-Modell die folgenden Szenarien:  
  
-   Erstellen eines Adapters, mit dem ein Host ein Add-In verwenden kann, das für eine vorherige Hostversion entwickelt wurde  
  
-   Erstellen eines Adapters, mit dem ein Host ein Add-In verwenden kann, das für eine neuere Hostversion entwickelt wurde  
  
-   Erstellen eines Adapters, mit dem ein Host Add-Ins verwenden kann, die für einen anderen Host entwickelt wurden  
  
### <a name="discovery-and-activation"></a>Suche und Aktivierung  
 Sie können ein Add-In aktivieren, indem Sie ein Token aus einer Auflistung verwenden, die die in einem Informationsspeicher gefundenen Add-Ins darstellt. Add-Ins werden anhand des Typs gesucht, der die Hostansicht des Add-Ins definiert. Sie können auch ein bestimmtes Add-In anhand des Typs suchen, der das Add-In definiert. Der Informationsspeicher besteht aus zwei Cachedateien: dem Pipelinespeicher und dem Add-In-Speicher.  
  
 Informationen zum Aktualisieren und Neuerstellen des Informationsspeichers finden Sie unter [Add-in-Ermittlung](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421). Informationen zum Aktivieren von Add-Ins finden Sie unter [Add-in-Aktivierung](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) und [Vorgehensweise: Aktivieren von Add-Ins mit Unterschiedlicher Isolation und Sicherheit](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).  
  
### <a name="isolation-levels-and-external-processes"></a>Isolationsstufen und externe Prozesse  
 Das Add-In-Modell unterstützt mehrere Isolationsstufen zwischen einem Add-In und dessen Host oder zwischen Add-Ins. Beginnend mit der niedrigsten Isolationsstufe werden die folgenden Stufen unterstützt:  
  
-   Das Add-In wird in derselben Anwendungsdomäne wie der Host ausgeführt. Dies ist nicht empfehlenswert, weil Sie die Isolations- und Entladefunktionen verlieren, über die Sie verfügen, wenn Sie unterschiedliche Anwendungsdomänen verwenden.  
  
-   Mehrere Add-Ins werden in dieselbe Anwendungsdomäne geladen, die sich von der vom Host verwendeten Anwendungsdomäne unterscheidet.  
  
-   Jedes Add-In wird ausschließlich in die eigene Anwendungsdomäne geladen. Dies ist die am häufigsten verwendete Isolationsstufe.  
  
-   Mehrere Add-Ins werden in einem externen Prozess in dieselbe Anwendungsdomäne geladen.  
  
-   Jedes Add-In wird in einem externen Prozess ausschließlich in die eigene Anwendungsdomäne geladen. Dies ist das Szenario mit der stärksten Isolation.  
  
 Weitere Informationen zur Verwendung externer Prozesse finden Sie unter [Vorgehensweise: Aktivieren von Add-Ins mit Unterschiedlicher Isolation und Sicherheit](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).  
  
### <a name="lifetime-management"></a>Verwaltung der Lebensdauer  
 Da das Add-In-Modell Anwendungsdomänen- und Prozessgrenzen überschreitet, reicht die Garbage Collection nicht aus, um Objekte freizugeben. Das Add-In-Modell bietet einen Mechanismus zur Verwaltung der Lebensdauer, der Token und Referenzzähler verwendet und in der Regel keine zusätzliche Programmierung erfordert. Weitere Informationen finden Sie unter [Lebenszeitverwaltung](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
 [Zurück zum Anfang](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a>Unterscheiden zwischen Add-Ins und Hosts  
 Der Unterschied zwischen einem Add-In und einem Host besteht darin, dass der Host die Komponente ist, die das Add-In aktiviert. Der Host kann die größere der beiden Komponenten, beispielsweise eine Textverarbeitungsanwendung mit ihren Rechtschreibprüfungen, oder die kleinere der beiden Komponenten sein, beispielsweise ein Instant Messaging-Client mit einem eingebetteten Media Player. Das Add-In-Modell unterstützt Add-Ins sowohl in Client- als auch in Serverszenarien. Beispiele für Server-Add-Ins sind Add-Ins, die Virenüberprüfung, Spamfilter und IP-Schutz für Mailserver bieten. Beispiele für Client-add-Ins sind Referenz-add-ins für Textverarbeitungsprogramme, spezielle Funktionen für Grafikprogramme und Spiele sowie virenüberprüfung für lokale e-Mail-Clients.  
  
 [Zurück zum Anfang](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)|Beschreibt die Kommunikationspipeline von Segmenten von der Hostanwendung zum Add-In. Enthält Codebeispiele in exemplarischen Vorgehensweisen. Darin wird beschrieben, wie Sie die Pipeline erstellen und Segmente für die Pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]bereitstellen.|  
|[Anwendungsdomänen und Assemblys](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|Beschreibt die Beziehung zwischen Anwendungsdomänen, die eine Isolationsgrenze zwecks Sicherheit, Zuverlässigkeit und Versionsverwaltung bereitstellen, und Assemblys.|  
  
 [Zurück zum Anfang](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>Verweis  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [Zurück zum Anfang](#top)