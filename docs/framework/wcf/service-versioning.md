---
title: Dienstversionsverwaltung
ms.date: 03/30/2017
ms.assetid: 37575ead-d820-4a67-8059-da11a2ab48e2
ms.openlocfilehash: 3f9fd87eacf67a1b23568dcf87df086e935879ba
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423686"
---
# <a name="service-versioning"></a>Dienstversionsverwaltung
Nach der ursprünglichen Bereitstellung und möglicherweise mehreren Bereitstellungen während ihrer Lebensdauer müssen die Dienste (und die Endpunkte, die sie verfügbar machen) eventuell geändert werden. Dafür kann es verschiedene Gründe geben, z.&#160;B. veränderte Geschäftsanforderungen, Anforderungen an die Informationstechnologie oder andere Themen, die in die Dienste integriert werden müssen. Jede Änderung führt zu einer neuen Version des Diensts. In diesem Thema wird erläutert, wie Sie die Versionsverwaltung in Windows Communication Foundation (WCF) in Erwägung gezogen.  
  
## <a name="four-categories-of-service-changes"></a>Vier Kategorien von Dienständerungen  
 Die Änderungen von Diensten, die eventuell erforderlich sind, können in vier Kategorien unterteilt werden:  
  
- Vertragsänderungen: Ein Vorgang wird z.&#160;B. hinzugefügt, oder ein Datenelement in einer Nachricht wird hinzugefügt oder geändert.  
  
- Adressänderungen: Ein Dienst wird z.&#160;B. an einen anderen Speicherort verschoben, an dem die Endpunkte neue Adressen aufweisen.  
  
- Bindungsänderungen: Ein Sicherheitsmechanismus oder seine Einstellungen werden z.&#160;B. geändert.  
  
- Implementierungsänderungen: Wenn sich z.&#160;B. eine interne Methodenimplementierung ändert.  
  
 Einige dieser Änderungen werden als "unterbrechend" und andere als "nicht unterbrechend" bezeichnet. Eine Änderung ist *nicht unterbrechend* , wenn alle Nachrichten, die in der vorherigen Version erfolgreich verarbeitet worden wären, in der neuen Version erfolgreich verarbeitet werden. Jede Änderung, die dieses Kriterium nicht erfüllt, ist *eine wichtige* Änderung.  
  
## <a name="service-orientation-and-versioning"></a>Dienstausrichtung und Versionsverwaltung  
 Einer der Grundsätze der Dienstausrichtung ist, dass die Dienste und Clients autonom (oder unabhängig) sind. Unter anderem impliziert dies, dass die Dienstentwickler nicht davon ausgehen können, dass sie alle Dienstclients steuern oder sogar kennen. Dies beeinträchtigt die Möglichkeit, alle Clients neu zu erstellen und neu bereitzustellen, wenn die Version eines Diensts geändert wird. In diesem Thema wird davon ausgegangen, dass der Dienst diesem Grundsatz folgt und daher unabhängig von den Clients geändert oder "versionsverwaltet" werden muss.  
  
 In den Fällen, in denen keine unterbrechende Änderung erwartet wird und diese nicht verhindert werden kann, kann dieser Grundsatz von einer Anwendung ignoriert werden. Dadurch wird es dann erforderlich, dass die Clients neu erstellt und mit einer neueren Version des Diensts bereitgestellt werden.  
  
## <a name="contract-versioning"></a>Vertragsversionsverwaltung  
 Von einem Client verwendete Verträge müssen nicht dem Vertrag entsprechen, der vom Dienst verwendet wird. Sie müssen lediglich kompatibel sein.  
  
 Für Dienstverträge bedeutet Kompatibilität, dass neue, vom Dienst verfügbar gemachte Vorgänge hinzugefügt, vorhandene Vorgänge jedoch nicht entfernt oder semantisch geändert werden können.  
  
 Für Datenverträge bedeutet Kompatibilität, dass neue Schematypdefinitionen hinzugefügt, vorhandene Schematypdefinitionen jedoch nicht auf die unterbrechende Art geändert werden können. Zu den unterbrechenden Änderungen können das Entfernen von Datenmembern oder das Ändern ihrer Datentypinkompatibilität gehören. Diese Funktion bietet dem Dienst einigen Spielraum zum Ändern seiner Vertragsversionen, ohne Clients zu unterbrechen. In den nächsten beiden Abschnitten werden nicht unterbrechende und wichtige Änderungen erläutert, die an WCF-Daten und-Dienstverträgen vorgenommen werden können.  
  
## <a name="data-contract-versioning"></a>Datenvertragsversionsverwaltung  
 In diesem Abschnitt wird die Datenversionsverwaltung für die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse und die <xref:System.Runtime.Serialization.DataContractAttribute>-Klasse beschrieben.  
  
### <a name="strict-versioning"></a>Strenge Versionsverwaltung  
 In vielen Szenarien, in denen das Ändern der Versionen ein Problem darstellt, hat der Dienstentwickler keine Kontrolle über die Clients und kann deshalb keine Annahmen darüber abgeben, wie sie auf Änderungen in der Nachrichten-XML oder im Schema reagieren würden. In diesen Fällen müssen Sie sicherstellen, dass die neuen Nachrichten aus zwei Gründen anhand des alten Schemas überprüft werden:  
  
- Die alten Clients wurden mit der Annahme entwickelt, dass sich das Schema nicht ändert. Sie können eventuell keine Nachrichten verarbeiten, für die sie nicht vorgesehen waren.  
  
- Die alten Clients können eventuell anhand des alten Schemas eine tatsächliche Schemavalidierung durchführen, bevor sie versuchen, die Nachrichten zu verarbeiten.  
  
 Die empfohlene Methode in solchen Szenarien besteht darin, vorhandene Datenverträge als unveränderlich zu behandeln und neue Verträge mit eindeutigen qualifizierten XML-Namen zu erstellen. Der Dienstentwickler würde dann entweder einem bereits vorhandenen Dienstvertrag neue Methoden hinzufügen oder einen neuen Dienstvertrag mit Methoden erstellen, die den neuen Datenvertrag verwenden.  
  
 Es wird häufig der Fall sein, dass ein Dienstentwickler einen Teil der Geschäftslogik schreiben muss, der in allen Versionen eines Datenvertrags ausgeführt werden sollte, sowie zusätzlich versionsspezifischen Geschäftscode für jede Version des Datenvertrags. Im Anhang am Ende dieses Themas wird erläutert, wie die Schnittstellen verwendet werden können, um diese Anforderung zu erfüllen.  
  
### <a name="lax-versioning"></a>Weniger strenge Versionsverwaltung  
 In vielen anderen Szenarien kann der Dienstentwickler davon ausgehen, dass das Hinzufügen eines neuen, optionalen Members zum Datenvertrag keine vorhandenen Clients unterbricht. Dazu muss der Dienstentwickler überprüfen, ob die vorhandenen Clients keine Schemavalidierung durchführen und dass sie unbekannte Datenmember ignorieren. In diesen Szenarien ist es möglich, die Datenvertragsfunktionen zum Hinzufügen neuer Member auf eine nicht unterbrechende Weise zu nutzen. Der Dienstentwickler kann diese Annahme machen, wenn die Datenvertragsfunktionen für die Versionsverwaltung bereits für die erste Version des Diensts verwendet wurden.  
  
 WCF, ASP.NET-Webdienste und viele andere Webdienst Stapel unterstützen die *Lax-Versions*Verwaltung, d. h., Sie lösen keine Ausnahmen für neue unbekannte Datenmember in empfangenen Daten aus.  
  
 Häufig wird fälschlicherweise angenommen, dass die vorhandenen Clients durch das Hinzufügen eines neuen Members nicht unterbrochen werden können. Falls Sie sich nicht sicher sind, ob alle Clients für die weniger strenge Versionsverwaltung ausgerichtet sind, wird empfohlen, die strengen Richtlinien zur Versionsverwaltung zu verwenden und die Datenverträge als unveränderlich zu behandeln.  
  
 Ausführliche Richtlinien für die Lax-und strikte Versionsverwaltung von Daten Verträgen finden Sie unter [bewährte Methoden: Versions](best-practices-data-contract-versioning.md)Verwaltung von Daten Verträgen.  
  
### <a name="distinguishing-between-data-contract-and-net-types"></a>Unterscheidung zwischen Datenvertrags- und .NET-Typen  
 Eine .NET-Klasse oder eine Struktur kann als Datenvertrag projiziert werden, indem Sie der Klasse das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut hinzufügen. Der .NET-Typ und seine Datenvertragsprojektionen sind zwei verschiedene Dinge. Es können mehrere .NET-Typen mit derselben Datenvertragsprojektion vorhanden sein. Diese Unterscheidung ist besonders nützlich, wenn Sie den .NET-Typ ändern und gleichzeitig den projizierten Datenvertrag beibehalten möchten, wobei Sie gleichzeitig die Kompatibilität mit den bereits vorhandenen Clients bewahren. Sie sollten immer die folgenden beiden Maßnahmen ergreifen, um diese Unterscheidung zwischen .NET-Typ und Datenvertrag beizubehalten:  
  
- Geben Sie einen <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> und einen <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> an. Sie sollten immer den Namen und den Namespace Ihres Datenvertrags angeben, um zu verhindern, dass der Name und der Namespace Ihres .NET-Typs im Vertrag verfügbar gemacht wird. Auf diese Weise bleibt der Datenvertrag derselbe, wenn Sie den .NET-Namespace oder -Typnamen zu einem späteren Zeitpunkt ändern möchten.  
  
- Geben Sie <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>an. Sie sollten immer den Namen Ihrer Datenmember angeben, um zu verhindern, dass der Name des .NET-Members im Vertrag verfügbar gemacht wird. Auf diese Weise bleibt der Datenvertrag derselbe, wenn Sie den .NET-Namen des Members zu einem späteren Zeitpunkt ändern möchten.  
  
### <a name="changing-or-removing-members"></a>Ändern oder Entfernen von Membern  
 Wenn Sie den Namen oder Datentyp eines Members ändern oder Datenmember entfernen, ist dies eine unterbrechende Änderung, auch wenn die weniger strenge Versionsverwaltung zulässig ist. Falls dies erforderlich ist, müssen Sie einen neuen Datenvertrag erstellen.  
  
 Falls die Dienstkompatibilität von hoher Wichtigkeit ist, sollten Sie die nicht verwendeten Datenmember in Ihrem Code ignorieren und sie unverändert lassen. Falls Sie einen Datenmember in mehrere Member aufteilen, sollten Sie erwägen, den vorhandenen Member als eine Eigenschaft unverändert zu lassen, mit der die erforderliche Aufteilung und erneute Aggregation für Clients auf niedrigeren Ebenen (Clients ohne Upgrade auf die neueste Version) durchgeführt werden.  
  
 Ähnlich verhält es sich mit Änderungen des Namens oder Namespace eines Datenvertrags, bei denen es sich ebenfalls um unterbrechende Änderungen handelt.  
  
### <a name="round-trips-of-unknown-data"></a>Round-Trips von unbekannten Daten  
 In einigen Szenarien muss ein "Round-Trip" von unbekannten Daten stattfinden, die aus Membern stammen, die einer neuen Version hinzugefügt wurden. So sendet z.&#160;B. ein "versionNew"-Dienst Daten mit einigen neu hinzugefügten Membern an einen "versionOld"-Client. Der Client ignoriert die neu hinzugefügten Member beim Verarbeiten der Nachricht, sendet dann jedoch diese Daten, einschließlich der neu hinzugefügten Member, erneut zurück an den versionNew-Dienst. Das typische Szenario dafür sind Datenupdates, bei denen Daten aus dem Dienst entfernt, geändert und zurückgegeben werden.  
  
 Um die Roundtrip-Funktion für einen bestimmten Typ zu aktivieren, muss der Typ die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle implementieren. Die Schnittstelle enthält die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft, die den <xref:System.Runtime.Serialization.ExtensionDataObject>-Typ zurückgibt. In der Eigenschaft werden alle Daten aus zukünftigen Versionen des Datenvertrags gespeichert, der in der aktuellen Version unbekannt ist. Diese Daten sind für den Client nicht transparent. Wenn jedoch die Instanz serialisiert wird, wird der Inhalt der <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft mit den restlichen Daten der Datenvertragsmember geschrieben.  
  
 Es wird empfohlen, dass alle Typen diese Schnittstelle implementieren, um neue und unbekannte zukünftige Member aufzunehmen.  
  
### <a name="data-contract-libraries"></a>Datenvertragsbibliotheken  
 Es können Bibliotheken mit Datenverträgen vorhanden sein, für die ein Vertrag in einem zentralen Repository veröffentlicht wird. Die Dienst- und Typimplementierer implementieren Datenverträge aus diesem Repository und machen diese so verfügbar. In diesem Fall können Sie beim Veröffentlichen eines Datenvertrags im Repository nicht steuern, wer Typen erstellt, die ihn implementieren. Sie können also den Vertrag nicht ändern, wenn er erst einmal veröffentlicht wurde, da er dadurch unveränderlich geworden ist.  
  
### <a name="when-using-the-xmlserializer"></a>Verwenden des XmlSerializer  
 Dieselben Versionsverwaltungsgrundlagen gelten, wenn Sie die <xref:System.Xml.Serialization.XmlSerializer>-Klasse verwenden. Wenn die strenge Versionsverwaltung erforderlich ist, sollten Sie die Datenverträge als unveränderlich behandeln und neue Datenverträge mit eindeutigen, qualifizierten Namen für die neuen Versionen erstellen. Wenn Sie sicher sind, dass die weniger strenge Versionsverwaltung verwendet werden kann, können Sie neue serialisierbare Member in neuen Versionen hinzufügen, bereits vorhandene Member jedoch nicht ändern oder entfernen.  
  
> [!NOTE]
> Der <xref:System.Xml.Serialization.XmlSerializer> verwendet das <xref:System.Xml.Serialization.XmlAnyElementAttribute>-Attribut und das <xref:System.Xml.Serialization.XmlAnyAttributeAttribute>-Attribut, um Round-Trips von unbekannten Daten zu unterstützen.  
  
## <a name="message-contract-versioning"></a>Versionsverwaltung für Nachrichtenverträge  
 Die Richtlinien für die Versionsverwaltung von Nachrichtenverträgen sind ähnlich wie diejenigen für die Versionsverwaltung von Datenverträgen. Falls eine strenge Versionsverwaltung erforderlich ist, sollten Sie den Nachrichtentext nicht ändern, sondern stattdessen einen neuen Nachrichtenvertrag mit einem eindeutig qualifizierten Namen erstellen. Wenn Sie sicher sind, dass Sie die weniger strenge Versionsverwaltung verwenden können, können Sie neue Teile des Nachrichtentexts hinzufügen, die bereits vorhandenen jedoch nicht ändern oder entfernen. Diese Richtlinie gilt sowohl für reine als auch für eingeschlossene Nachrichtenverträge.  
  
 Nachrichtenheader können immer hinzugefügt werden, auch wenn die strenge Versionsverwaltung verwendet wird. Das MustUnderstand-Flag kann sich auf die Versionsverwaltung auswirken. Im Allgemeinen ist das Versions Verwaltungsmodell für Header in WCF wie in der SOAP-Spezifikation beschrieben.  
  
## <a name="service-contract-versioning"></a>Versionsverwaltung für Dienstverträge  
 Ähnlich wie bei der Versionsverwaltung für Datenverträge umfasst die Versionsverwaltung für Dienstverträge auch das Hinzufügen, Ändern und Entfernen von Vorgängen.  
  
### <a name="specifying-name-namespace-and-action"></a>Angeben von Name, Namespace und Aktion  
 Standardmäßig entspricht der Name eines Dienstvertrags dem Namen der Schnittstelle. Der Standard Namespace ist "http://tempuri.org", und jede Vorgangs Aktion ist "http://tempuri.org/contractname/methodname". Es wird empfohlen, explizit einen Namen und einen Namespace für den Dienstvertrag anzugeben, und eine Aktion für jeden Vorgang, um zu vermeiden, dass "http://tempuri.org" verwendet wird, und um zu verhindern, dass Schnittstellen-und Methodennamen im Dienstvertrag verfügbar gemacht werden.  
  
### <a name="adding-parameters-and-operations"></a>Hinzufügen von Parametern und Vorgängen  
 Beim Hinzufügen von Vorgängen, die vom Dienst verfügbar gemacht werden, handelt es sich um eine nicht unterbrechende Änderung, da die vorhandenen Clients diese neuen Vorgänge nicht berücksichtigen müssen.  
  
> [!NOTE]
> Beim Hinzufügen von Vorgängen zu einem Duplexrückrufvertrag handelt es sich um eine unterbrechende Änderung.  
  
### <a name="changing-operation-parameter-or-return-types"></a>Ändern von Vorgangsparametern oder Rückgabetypen  
 Beim Ändern von Parametern oder Rückgabetypen handelt es sich im Allgemeinen um eine unterbrechende Änderung, solange der neue Typ denselben Datenvertrag implementiert wie dies beim alten Typ der Fall ist. Um eine solche Änderung durchzuführen, fügen Sie dem Dienstvertrag einen neuen Vorgang hinzu oder definieren einen neuen Dienstvertrag.  
  
### <a name="removing-operations"></a>Entfernen von Vorgängen  
 Beim Entfernen von Vorgängen handelt es sich ebenfalls um eine unterbrechende Änderung. Um eine solche Änderung durchzuführen, definieren Sie einen neuen Dienstvertrag und machen ihn einem neuen Endpunkt verfügbar.  
  
### <a name="fault-contracts"></a>Fehlerverträge  
 Mit dem <xref:System.ServiceModel.FaultContractAttribute>-Attribut kann ein Dienstvertragentwickler Informationen über Fehler angeben, die von den Vertragsvorgängen zurückgegeben werden können.  
  
 Die Liste der in einem Dienstvertrag beschriebenen Fehler wird nicht als vollständig betrachtet. Ein Vorgang kann jederzeit Fehler zurückgeben, die in seinem Vertrag nicht beschrieben sind. Deshalb werden Änderungen der im Vertrag beschriebenen Fehler nicht als unterbrechend betrachtet. Beispielsweise das Hinzufügen eines neuen Fehlers zum Vertrag mithilfe von <xref:System.ServiceModel.FaultContractAttribute> oder das Entfernen eines vorhandenen Fehlers aus dem Vertrag.  
  
### <a name="service-contract-libraries"></a>Dienstvertragsbibliotheken  
 In Organisationen können Bibliotheken mit Verträgen vorhanden sein. Dabei wird ein Vertrag in einem zentralen Repository veröffentlicht, und die Dienstimplementierer implementieren Datenverträge aus diesem Repository. In diesem Fall können Sie beim Veröffentlichen eines Dienstvertrags im Repository nicht steuern, wer Dienste erstellt, die ihn implementieren. Sie können daher den Dienstvertrag nicht ändern, nachdem er veröffentlicht wurde, da er dadurch unveränderlich wird. WCF unterstützt die Vertrags Vererbung, die verwendet werden kann, um einen neuen Vertrag zu erstellen, der vorhandene Verträge erweitert. Wenn Sie diese Funktion verwenden möchten, müssen Sie eine neue Dienstvertragsschnittstelle definieren, die von der alten Dienstvertragsschnittstelle erbt, und dann der neuen Schnittstelle Methoden hinzufügen. Anschließend ändern Sie den Dienst, der den alten Vertrag implementiert, um den neuen Vertrag zu implementieren, und ändern die "versionOld"-Endpunktdefinition für die Verwendung des neuen Vertrags. Für "versionOld"-Clients erscheint der Endpunkt weiterhin als "versionOld"-Vertrag; für "versionNew"-Clients erscheint der Endpunkt als "versionNew"-Vertrag.  
  
## <a name="address-and-binding-versioning"></a>Versionsverwaltung von Adressen und Bindungen  
 Bei Änderungen an der Endpunktadresse und -bindung handelt es sich um unterbrechende Änderungen, solange die Clients die neue Endpunktadresse oder -bindung nicht dynamisch erkennen können. Ein Mechanismus zur Implementierung dieser Funktion ist die Verwendung einer UDDI-Registrierung sowie des UDDI-Aufrufmusters, bei der ein Client versucht, mit einem Endpunkt zu kommunizieren und im Falle eines Scheiterns eine bekannte UDDI-Registrierung für die aktuellen Endpunktdaten abfragt. Der Client verwendet dann die Adresse und die Bindung aus diesen Metadaten, um mit dem Endpunkt zu kommunizieren. Wenn diese Kommunikation erfolgreich ist, speichert der Client die Adress- und Bindungsinformationen für eine spätere Verwendung zwischen.  
  
## <a name="routing-service-and-versioning"></a>Routingdienst und Versionsverwaltung  
 Wenn es sich bei an einem Dienst vorgenommenen Änderungen um unterbrechende Änderungen handelt und Sie zwei oder mehr verschiedene Versionen eines Diensts gleichzeitig ausführen müssen, können Sie mit dem WCF-Routingdienst Meldungen an die entsprechende Dienstinstanz weiterleiten. Der WCF-Routingdienst führt inhaltsbasiertes Routing aus. Mit anderen Worten: Anhand von Informationen innerhalb der Nachricht wird bestimmt, an welches Ziel die Nachricht weitergeleitet wird. Weitere Informationen zum WCF-Routing Dienst finden Sie unter [Routing Dienst](./feature-details/routing-service.md). Ein Beispiel für die Verwendung des WCF-Routing diensdienstanbieter für die Dienst Versionsverwaltung finden Sie unter Gewusst [wie: Dienst Versionsverwaltung](./feature-details/how-to-service-versioning.md).  
  
## <a name="appendix"></a>Anhang  
 Die allgemeine Richtlinie für die Datenvertrags-Versionsverwaltung im Falle der strengen Versionsverwaltung besagt, dass Datenverträge als unveränderlich behandelt werden und neue Verträge erstellt werden, wenn Änderungen erforderlich sind. Für jeden neuen Datenvertrag muss eine neue Klasse erstellt werden. Deshalb ist ein Mechanismus erforderlich, mit dem vermieden wird, dass bereits vorhandener Code, der für die alte Datenvertragsklasse geschrieben wurde, für die neue Datenvertragsklasse neu geschrieben werden muss.  
  
 Ein solcher Mechanismus besteht z.&#160;B. in der Verwendung der Schnittstellen für die Definition der Member eines Datenvertrags und im Schreiben eines internen Implementierungscodes für die Schnittstellen anstatt der Datenvertragsklassen, mit denen die Schnittstellen implementiert werden. Im folgenden Code für Version 1 eines Diensts werden eine `IPurchaseOrderV1`-Schnittstelle und eine `PurchaseOrderV1`-Schnittstelle dargestellt:  
  
```csharp  
public interface IPurchaseOrderV1  
{  
    string OrderId { get; set; }  
    string CustomerId { get; set; }  
}  
  
[DataContract(  
Name = "PurchaseOrder",  
Namespace = "http://examples.microsoft.com/WCF/2005/10/PurchaseOrder")]  
public class PurchaseOrderV1 : IPurchaseOrderV1  
{  
    [DataMember(...)]  
    public string OrderId {...}  
    [DataMember(...)]  
    public string CustomerId {...}  
}  
```  
  
 Während die Vorgänge des Dienstvertrags im Sinne von `PurchaseOrderV1` geschrieben werden würden, würde die tatsächliche Geschäftslogik `IPurchaseOrderV1` entsprechen. In Version 2 würde es dann eine neue `IPurchaseOrderV2`-Schnittstelle und eine neue `PurchaseOrderV2`-Klasse geben, wie im folgenden Code dargestellt:  
  
```csharp
public interface IPurchaseOrderV2  
{  
    DateTime OrderDate { get; set; }  
}

[DataContract(   
Name = "PurchaseOrder",  
Namespace = "http://examples.microsoft.com/WCF/2006/02/PurchaseOrder")]  
public class PurchaseOrderV2 : IPurchaseOrderV1, IPurchaseOrderV2  
{  
    [DataMember(...)]  
    public string OrderId {...}  
    [DataMember(...)]  
    public string CustomerId {...}  
    [DataMember(...)]  
    public DateTime OrderDate { ... }  
}  
```  
  
 Der Dienstvertrag würde aktualisiert werden, um neue Vorgänge für `PurchaseOrderV2` zu berücksichtigen. Die vorhandene Geschäftslogik für `IPurchaseOrderV1` würde weiterhin für `PurchaseOrderV2` funktionieren. Es würde eine neue Geschäftslogik für `OrderDate` geschrieben, die die `IPurchaseOrderV2`-Eigenschaft benötigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>
- <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>
- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>
- <xref:System.Xml.Serialization.XmlSerializer>
- [Datenvertragsäquivalenz](./feature-details/data-contract-equivalence.md)
- [Versionstolerante Serialisierungsrückrufe](./feature-details/version-tolerant-serialization-callbacks.md)
