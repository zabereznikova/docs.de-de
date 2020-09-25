---
title: Datendienst-Versionskontrolle (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: 8d7cc0f0033c75c05ac9c39cfbf1ce09dc032a4c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91182869"
---
# <a name="data-service-versioning-wcf-data-services"></a>Datendienst-Versionskontrolle (WCF Data Services)

Mit dem Open Data Protocol (odata) können Sie Datendienste erstellen, damit Clients mithilfe von URIs, die auf einem Datenmodell basieren, auf Daten als Ressourcen zugreifen können. Odata unterstützt auch die Definition von Dienst Vorgängen. Nach der ursprünglichen Bereitstellung und möglicherweise mehreren Bereitstellungen während ihrer Lebensdauer müssen diese Datendienste eventuell geändert werden. Dafür kann es verschiedene Gründe geben, z. B. veränderte Geschäftsanforderungen, Anforderungen an die Informationstechnologie oder andere Themen, die in die Dienste integriert werden müssen. Wenn Sie Änderungen an einem vorhandenen Datendienst vornehmen, müssen Sie berücksichtigen, ob eine neue Version des Datendiensts definiert wird und wie die Auswirkungen auf vorhandene Clientanwendungen am besten minimiert werden. Dieses Thema enthält einen Leitfaden, wann und wie eine neue Version eines Datendiensts erstellt wird. Außerdem wird beschrieben, wie WCF Data Services einen Austausch zwischen Clients und Datendiensten behandelt, die unterschiedliche Versionen des odata-Protokolls unterstützen.

## <a name="versioning-a-wcf-data-service"></a>Versionskontrolle eines WCF Data Service

 Sobald ein Datendienst bereitgestellt wird und die Daten genutzt werden, können Änderungen am Datendienst zu Kompatibilitätsproblemen mit vorhandenen Clientanwendungen führen. Da Änderungen aber oft aufgrund der übergreifenden Geschäftsanforderungen des Diensts erforderlich sind, müssen Sie berücksichtigen, wann und wie eine neue Version des Datendiensts mit den geringsten Auswirkungen auf Clientanwendungen erstellt wird.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Datenmodelländerungen, die eine neue Version des Datendiensts empfehlen

 Wenn Sie die Veröffentlichung einer neuen Version eines Datendiensts in Betracht ziehen, ist es wichtig, zu verstehen, wie die anderen Arten von Änderungen sich möglicherweise auf Clientanwendungen auswirken. Änderungen an einem Datendienst, die möglicherweise die Erstellung einer neuen Version eines Datendiensts erforderlich machen, können in die folgenden beiden Kategorien unterteilt werden:

- Änderungen am Dienstvertrag – darunter Aktualisierungen für Dienstvorgänge, Änderungen hinsichtlich des Zugriffs auf Entitätenmengen (Feeds), Versionsänderungen und andere Änderungen bezüglich Dienstverhaltensweisen.

- Änderungen am Datenvertrag – darunter Änderungen am Datenmodell, an Feedformaten oder Feedanpassungen.

 Die folgende Tabelle führt die Arten von Änderungen auf, für die das Veröffentlichen einer neuen Version des Datendiensts in Betracht gezogen werden sollte:

|Art der Änderung|Erfordert eine neue Version|Neue Version ist nicht erforderlich|
|--------------------|----------------------------|----------------------------|
|Dienstvorgänge|-Neuen Parameter hinzufügen<br />-Rückgabetyp ändern<br />-Dienst Vorgang entfernen|-Vorhandenen Parameter löschen<br />-Neuen Dienst Vorgang hinzufügen|
|Dienstverhaltensweisen|-Anzahl Anforderungen deaktivieren<br />-Unterstützung für Projektion deaktivieren<br />-Erhöhen der erforderlichen Datendienst Version|-Aktivieren von count-Anforderungen<br />-Unterstützung für Projektion aktivieren<br />-Verringern der erforderlichen Datendienst Version|
|Entitätenmengenberechtigungen|-Berechtigungen für Entitätenmenge einschränken<br />-Antwort Code ändern (neuer erster Ziffern Wert) <sup>1</sup>|-Berechtigungen für Entitätenmenge lockern<br />-Antwort Code ändern (gleicher erster Ziffern Wert)|
|Entitätseigenschaften|-Vorhandene Eigenschaft oder Beziehung entfernen<br />-Eigenschaft hinzufügen, die keine NULL-Werte zulässt<br />-Vorhandene Eigenschaft ändern|-NULL able-Eigenschaft hinzufügen<sup>2</sup>|
|Entitätenmengen|-Entitätenmenge entfernen|-Abgeleiteten Typ hinzufügen<br />-Basistyp ändern<br />-Entitätenmenge hinzufügen|
|Feedanpassung|-Entitäts Eigenschafts Zuordnung ändern||

 <sup>1</sup> dies hängt möglicherweise davon ab, wie streng eine Client Anwendung auf den Empfang eines bestimmten Fehlercodes basiert.

 <sup>2</sup> Sie können die- <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> Eigenschaft auf festlegen `true` , damit der Client alle neuen Eigenschaften ignoriert, die vom Datendienst gesendet werden, die nicht auf dem Client definiert sind. Wenn aber Einfügungen vorgenommen werden, werden die nicht vom Client einbezogenen Eigenschaften in der POST-Anforderung auf ihre Standardwerte festgelegt. Bei Aktualisierungen können vorhandene Daten in einer Eigenschaft, die dem Client nicht bekannt ist, mit Standardwerten überschrieben werden. In diesem Fall sollten Sie die Aktualisierung als MERGE-Anforderung senden. Dies ist die Standardeinstellung. Weitere Informationen finden Sie unter [Verwalten des Datendienst Kontexts](managing-the-data-service-context-wcf-data-services.md).

### <a name="how-to-version-a-data-service"></a>So versionieren Sie einen Datendienst

 Bei Bedarf wird eine neue Datendienstversion definiert, indem eine neue Instanz des Diensts mit einem aktualisierten Dienstvertrag oder einem Datenmodell erstellt wird. Dieser neue Dienst wird dann mit einem neuen URI-Endpunkt verfügbar gemacht, der sich von der früheren Version unterscheidet. Zum Beispiel:

- Alte Version: `http://services.odata.org/Northwind/v1/Northwind.svc/`

- Neue Version: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Wenn Sie einen Datendienst aktualisieren, müssen Clients auch auf Grundlage der neuen Datendienstmetadaten aktualisiert werden und den neuen Stamm-URI verwenden. Wenn möglich, sollten Sie die frühere Version des Datendiensts beibehalten, um Clients zu unterstützen, die noch nicht für die Verwendung der neuen Version aktualisiert wurden. Frühere Versionen eines Datendiensts können entfernt werden, wenn sie nicht mehr benötigt werden. Sie sollten erwägen, den Datendienstendpunkt-URI in einer externen Konfigurationsdatei beizubehalten.

## <a name="odata-protocol-versions"></a>OData-Protokollversionen

 Wenn neue Versionen von odata veröffentlicht werden, verwenden Client Anwendungen möglicherweise nicht dieselbe Version des odata-Protokolls, die vom Datendienst unterstützt wird. Eine ältere Client Anwendung greift möglicherweise auf einen Datendienst zu, der eine neuere Version von odata unterstützt. Eine Client Anwendung verwendet möglicherweise auch eine neuere Version der WCF Data Services-Client Bibliothek, die eine neuere Version von odata unterstützt als der Datendienst, auf den zugegriffen wird.

 WCF Data Services nutzt die von odata bereitgestellte Unterstützung, um derartige Versions Verwaltungs Szenarien zu verarbeiten. Es gibt auch Unterstützung für das Erstellen und Verwenden von Datenmodell Metadaten, um Client Datendienst Klassen zu erstellen, wenn der Client eine andere Version von odata verwendet, als vom Datendienst verwendet wird. Weitere Informationen finden Sie im Abschnitt Protokoll Versionsverwaltung im Artikel [odata: Übersicht](https://www.odata.org/documentation/odata-version-2-0/overview/) .

### <a name="version-negotiation"></a>Versionsaushandlung

 Der Datendienst kann so konfiguriert werden, dass er die höchste Version des odata-Protokolls definiert, das vom Dienst verwendet wird, unabhängig von der vom Client angeforderten Version. Hierfür können Sie einen <xref:System.Data.Services.Common.DataServiceProtocolVersion> Wert für die- <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> Eigenschaft von angeben, die <xref:System.Data.Services.DataServiceBehavior> vom Datendienst verwendet wird. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).

 Wenn eine Anwendung die WCF Data Services Client Bibliotheken für den Zugriff auf einen Datendienst verwendet, legen die Bibliotheken diese Header automatisch auf die richtigen Werte fest, abhängig von der Version von odata und den Funktionen, die in der Anwendung verwendet werden. Standardmäßig verwendet WCF Data Services die niedrigste Protokollversion, die den angeforderten Vorgang unterstützt.

 In der folgenden Tabelle werden die Versionen von .NET Framework und Silverlight erläutert, die WCF Data Services Unterstützung für bestimmte Versionen des odata-Protokolls enthalten.

|Odata-Protokoll Version|Unterstützt seit...|
|-----------------------------------------------------------------------------------|----------------------------|
|Version 1|-.NET Framework 3,5 Service Pack 1 (SP1)<br />-Silverlight, Version 3|
|Version 2|-.NET Framework 4<br />-Silverlight, Version 4|

### <a name="metadata-versions"></a>Metadatenversionen

 Standardmäßig verwendet WCF Data Services die CSDL-Version 1,1, um ein Datenmodell darzustellen. Dies ist immer bei Datenmodellen der Fall, die auf einem Reflektionsanbieter oder einem benutzerdefinierten Datendienstanbieter basieren. Wenn das Datenmodell jedoch mit dem Entity Framework definiert wird, wird diejenige CSDL-Version zurückgegeben, die vom Entity Framework verwendet wird. Die CSDL-Version wird durch den Namespace des [Schema-Elements (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#schema-element-csdl)bestimmt.

 Das `DataServices`-Element der zurückgegebenen Metadaten enthält auch ein `DataServiceVersion`-Attribut, das den gleichen Wert wie der `DataServiceVersion`-Header in der Antwortnachricht hat. Client Anwendungen, wie z. b. das Dialogfeld **Dienstverweis hinzufügen** in Visual Studio, verwenden diese Informationen zum Generieren von Client Datendienst Klassen, die ordnungsgemäß mit der Version von WCF Data Services funktionieren, die den Datendienst hosten. Weitere Informationen finden Sie im Abschnitt Protokoll Versionsverwaltung im Artikel [odata: Übersicht](https://www.odata.org/documentation/odata-version-2-0/overview/) .

## <a name="see-also"></a>Weitere Informationen

- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Definieren von WCF Data Services](defining-wcf-data-services.md)
