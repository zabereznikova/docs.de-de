---
title: Datendienst-Versionskontrolle (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: f82ab4c98e724bbed658a6c77de9c5a5d5c3390f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121530"
---
# <a name="data-service-versioning-wcf-data-services"></a>Datendienst-Versionskontrolle (WCF Data Services)
Mit dem Open Data Protocol (OData) können Sie Datendienste erstellen, damit Clients mithilfe von URIs, die auf einem Datenmodell basieren, auf Daten als Ressourcen zugreifen können. OData unterstützt auch die Definition von Dienstvorgängen. Nach der ursprünglichen Bereitstellung und möglicherweise mehreren Bereitstellungen während ihrer Lebensdauer müssen diese Datendienste eventuell geändert werden. Dafür kann es verschiedene Gründe geben, z. B. veränderte Geschäftsanforderungen, Anforderungen an die Informationstechnologie oder andere Themen, die in die Dienste integriert werden müssen. Wenn Sie Änderungen an einem vorhandenen Datendienst vornehmen, müssen Sie berücksichtigen, ob eine neue Version des Datendiensts definiert wird und wie die Auswirkungen auf vorhandene Clientanwendungen am besten minimiert werden. Dieses Thema enthält einen Leitfaden, wann und wie eine neue Version eines Datendiensts erstellt wird. Außerdem wird beschrieben, wie WCF Data Services einen Austausch zwischen Clients und Datendiensten verarbeitet, die verschiedene Versionen des OData-Protokolls unterstützen.

## <a name="versioning-a-wcf-data-service"></a>Versionskontrolle eines WCF Data Service
 Sobald ein Datendienst bereitgestellt wird und die Daten genutzt werden, können Änderungen am Datendienst zu Kompatibilitätsproblemen mit vorhandenen Clientanwendungen führen. Da Änderungen aber oft aufgrund der übergreifenden Geschäftsanforderungen des Diensts erforderlich sind, müssen Sie berücksichtigen, wann und wie eine neue Version des Datendiensts mit den geringsten Auswirkungen auf Clientanwendungen erstellt wird.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Datenmodelländerungen, die eine neue Version des Datendiensts empfehlen
 Wenn Sie die Veröffentlichung einer neuen Version eines Datendiensts in Betracht ziehen, ist es wichtig, zu verstehen, wie die anderen Arten von Änderungen sich möglicherweise auf Clientanwendungen auswirken. Änderungen an einem Datendienst, die möglicherweise die Erstellung einer neuen Version eines Datendiensts erforderlich machen, können in die folgenden beiden Kategorien unterteilt werden:

- Änderungen am Dienstvertrag – darunter Aktualisierungen für Dienstvorgänge, Änderungen hinsichtlich des Zugriffs auf Entitätenmengen (Feeds), Versionsänderungen und andere Änderungen bezüglich Dienstverhaltensweisen.

- Änderungen am Datenvertrag – darunter Änderungen am Datenmodell, an Feedformaten oder Feedanpassungen.

 Die folgende Tabelle führt die Arten von Änderungen auf, für die das Veröffentlichen einer neuen Version des Datendiensts in Betracht gezogen werden sollte:

|Art der Änderung|Erfordert eine neue Version|Neue Version ist nicht erforderlich|
|--------------------|----------------------------|----------------------------|
|Dienstvorgänge|- Hinzufügen neuer Parameter<br />- Rückgabetyp ändern<br />- Service-Vorgang entfernen|- Löschen vorhandener Parameter<br />- Hinzufügen eines neuen Service-Vorgangs|
|Dienstverhaltensweisen|- Deaktivieren von Zählanforderungen<br />- Deaktivieren der Projektionsunterstützung<br />- Erhöhen Sie die erforderliche Datendienstversion|- Aktivieren von Zählanforderungen<br />- Projektionsunterstützung aktivieren<br />- Verringern der erforderlichen Datendienstversion|
|Entitätenmengenberechtigungen|- Einschränken von Entitätssatzberechtigungen<br />- Änderungsantwortcode (neuer erster Ziffernwert) <sup>1</sup>|- Relax-Entitätssatzberechtigungen<br />- Änderung stolieren Antwortcode (gleicher erster Ziffernwert)|
|Entitätseigenschaften|- Vorhandene Eigenschaft oder Beziehung entfernen<br />- Hinzufügen nicht nullierbarer Eigenschaft<br />- Bestehende Eigenschaft ändern|- Hinzufügen der nullablen Eigenschaft<sup>2</sup>|
|Entitätenmengen|- Entitätssatz entfernen|- Abgeleiteten Typ hinzufügen<br />- Ändern des Basistyps<br />- Hinzufügen eines Entitätssatzes|
|Feedanpassung|- Ändern der Entitätseigenschaftszuordnung||

 <sup>1</sup> Dies kann davon abhängen, wie streng eine Clientanwendung auf den Erhalt eines bestimmten Fehlercodes angewiesen ist.

 <sup>2</sup> Sie können <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> festlegen, dass die Eigenschaft so eingestellt `true` wird, dass der Client alle neuen Eigenschaften ignoriert, die vom Datendienst gesendet werden und nicht auf dem Client definiert sind. Wenn aber Einfügungen vorgenommen werden, werden die nicht vom Client einbezogenen Eigenschaften in der POST-Anforderung auf ihre Standardwerte festgelegt. Bei Aktualisierungen können vorhandene Daten in einer Eigenschaft, die dem Client nicht bekannt ist, mit Standardwerten überschrieben werden. In diesem Fall sollten Sie die Aktualisierung als MERGE-Anforderung senden. Dies ist die Standardeinstellung. Weitere Informationen finden Sie unter [Verwalten des Datendienstkontexts](managing-the-data-service-context-wcf-data-services.md).

### <a name="how-to-version-a-data-service"></a>So versionieren Sie einen Datendienst
 Bei Bedarf wird eine neue Datendienstversion definiert, indem eine neue Instanz des Diensts mit einem aktualisierten Dienstvertrag oder einem Datenmodell erstellt wird. Dieser neue Dienst wird dann mit einem neuen URI-Endpunkt verfügbar gemacht, der sich von der früheren Version unterscheidet. Beispiel:

- Alte Version: `http://services.odata.org/Northwind/v1/Northwind.svc/`

- Neue Version: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Wenn Sie einen Datendienst aktualisieren, müssen Clients auch auf Grundlage der neuen Datendienstmetadaten aktualisiert werden und den neuen Stamm-URI verwenden. Wenn möglich, sollten Sie die frühere Version des Datendiensts beibehalten, um Clients zu unterstützen, die noch nicht für die Verwendung der neuen Version aktualisiert wurden. Frühere Versionen eines Datendiensts können entfernt werden, wenn sie nicht mehr benötigt werden. Sie sollten erwägen, den Datendienstendpunkt-URI in einer externen Konfigurationsdatei beizubehalten.

## <a name="odata-protocol-versions"></a>OData-Protokollversionen
 Wenn neue Versionen von OData veröffentlicht werden, verwenden Clientanwendungen möglicherweise nicht dieselbe Version des OData-Protokolls, die vom Datendienst unterstützt wird. Eine ältere Clientanwendung kann auf einen Datendienst zugreifen, der eine neuere Version von OData unterstützt. Eine Clientanwendung verwendet möglicherweise auch eine neuere Version der WCF Data Services-Clientbibliothek, die eine neuere Version von OData unterstützt als der Datendienst, auf den zugegriffen wird.

 WCF Data Services nutzt die unterstützungsmittelartiver Unterstützung von OData, um solche Versionsszenarien zu verarbeiten. Es gibt auch Unterstützung für das Generieren und Verwenden von Datenmodellmetadaten zum Erstellen von Clientdatendienstklassen, wenn der Client eine andere Version von OData verwendet als der Datendienst. Weitere Informationen finden Sie im Abschnitt Protokollversionierung im Artikel [OData: Übersicht.](https://www.odata.org/documentation/odata-version-2-0/overview/)

### <a name="version-negotiation"></a>Versionsaushandlung
 Der Datendienst kann so konfiguriert werden, dass die höchste Version des OData-Protokolls definiert wird, die vom Dienst verwendet wird, unabhängig von der vom Client angeforderten Version. Sie können dies tun, indem Sie einen <xref:System.Data.Services.Common.DataServiceProtocolVersion> Wert für die <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> Eigenschaft der vom Datendienst <xref:System.Data.Services.DataServiceBehavior> verwendeten Angeben. Weitere Informationen finden Sie unter [Konfigurieren des Datendienstes](configuring-the-data-service-wcf-data-services.md).

 Wenn eine Anwendung die WCF Data Services-Clientbibliotheken für den Zugriff auf einen Datendienst verwendet, legen die Bibliotheken diese Header automatisch auf die richtigen Werte fest, abhängig von der Version von OData und den Features, die in der Anwendung verwendet werden. Standardmäßig verwendet WCF Data Services die niedrigste Protokollversion, die den angeforderten Vorgang unterstützt.

 In der folgenden Tabelle sind die Versionen von .NET Framework und Silverlight aufgeführt, die WCF Data Services-Unterstützung für bestimmte Versionen des OData-Protokolls enthalten.

|OData-Protokollversion|Unterstützt seit...|
|-----------------------------------------------------------------------------------|----------------------------|
|Version 1|- .NET Framework 3.5 Service Pack 1 (SP1)<br />- Silverlight Version 3|
|Version 2|- .NET Framework 4<br />- Silverlight Version 4|

### <a name="metadata-versions"></a>Metadatenversionen
 Standardmäßig verwendet WCF Data Services Version 1.1 von CSDL, um ein Datenmodell darzustellen. Dies ist immer bei Datenmodellen der Fall, die auf einem Reflektionsanbieter oder einem benutzerdefinierten Datendienstanbieter basieren. Wenn das Datenmodell jedoch mit dem Entity Framework definiert wird, wird diejenige CSDL-Version zurückgegeben, die vom Entity Framework verwendet wird. Die Version der CSDL wird durch den Namespace des [Schemaelements (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#schema-element-csdl)bestimmt.

 Das `DataServices`-Element der zurückgegebenen Metadaten enthält auch ein `DataServiceVersion`-Attribut, das den gleichen Wert wie der `DataServiceVersion`-Header in der Antwortnachricht hat. Clientanwendungen, z. B. das Dialogfeld **Dienstreferenz hinzufügen** in Visual Studio, verwenden diese Informationen, um Clientdatendienstklassen zu generieren, die ordnungsgemäß mit der Version von WCF Data Services funktionieren, die den Datendienst hosten. Weitere Informationen finden Sie im Abschnitt Protokollversionierung im Artikel [OData: Übersicht.](https://www.odata.org/documentation/odata-version-2-0/overview/)

## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Definieren von WCF Data Services](defining-wcf-data-services.md)
