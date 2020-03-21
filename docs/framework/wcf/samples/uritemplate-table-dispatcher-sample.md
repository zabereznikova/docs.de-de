---
title: Beispiel zum UriTemplate-Tabellenverteiler
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: aa4259f8c823bebf38b9689df92c45992cb55723
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143680"
---
# <a name="uritemplate-table-dispatcher-sample"></a>Beispiel zum UriTemplate-Tabellenverteiler
Die <xref:System.UriTemplateTable>-Klasse stellt eine wörterbuchähnliche assoziative Tabellenstruktur zum Arbeiten mit einem Satz von <xref:System.UriTemplate>-Instanzen bereit. Dieses Beispiel demonstriert eine grundlegende, mit `UriTemplateTable` erstellte Verteiler-Engine, ein allgemeines Verwendungsszenario für die `UriTemplateTable`-Klasse.  
  
 Dieses Beispiel demonstriert die folgenden Schlüsselkonzepte für die `UriTemplateTable`-Klasse:  
  
- Das Zuordnen von Delegaten mit `UriTemplates` in einer `UriTemplateTable`.  
  
- Das Verwenden <xref:System.UriTemplateTable.MatchSingle%2A>, um den richtigen Handlerdelegaten für einen bestimmten URI zu erhalten.  
  
- Das Aufrufen des Handlerdelegaten zum Verarbeiten der Anforderung.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
2. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a>Weitere Informationen

- [UriTemplate-Tabelle](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [Uritemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
