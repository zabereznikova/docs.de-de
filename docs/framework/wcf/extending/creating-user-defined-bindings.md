---
title: Erstellen benutzerdefinierter Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- user-defined bindings [WCF]
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
ms.openlocfilehash: ba40bcfd8a9e9fea1a422ed124b9a966819bf184
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257853"
---
# <a name="creating-user-defined-bindings"></a>Erstellen benutzerdefinierter Bindungen

Es gibt mehrere Möglichkeiten, Bindungen zu erstellen, die nicht vom System bereitgestellt werden:  
  
- Erstellen Sie eine benutzerdefinierte Bindung auf Grundlage der <xref:System.ServiceModel.Channels.CustomBinding>-Klasse, die einen Container darstellt, den Sie mit Bindungselementen füllen. Die benutzerdefinierte Bindung wird dann einem Dienstendpunkt hinzugefügt. Sie können die benutzerdefinierte Bindung entweder programmgesteuert oder in der Konfigurationsdatei einer Anwendung erstellen. Um das Bindungselement aus einer Anwendungskonfigurationsdatei verwenden zu können, muss es <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> erweitern. Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](custom-bindings.md) und <xref:System.ServiceModel.Channels.CustomBinding> .  
  
- Sie können eine Klasse erstellen, die von einer Standardbindung abgeleitet ist. Sie können beispielsweise eine Klasse von <xref:System.ServiceModel.WSHttpBinding> ableiten und die <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A>-Methode überschreiben, um Bindungselemente abzurufen und ein benutzerdefiniertes Bindungselement einzufügen oder einen bestimmten Wert für die Sicherheit festzulegen.  
  
- Sie können einen neuen <xref:System.ServiceModel.Channels.Binding>-Typ erstellen, um die Bindungsimplementierung vollständig zu steuern.  
  
## <a name="the-order-of-binding-elements"></a>Die Reihenfolge der Bindungselemente  

 Jedes Bindungselement stellt einen Verarbeitungsschritt beim Senden und Empfangen von Nachrichten dar. Zur Laufzeit erstellen Bindungselemente die Kanäle und die Listener, die notwendig sind, um ausgehende und eingehende Kanalstapel zu erstellen.  
  
 Es gibt drei Haupttypen von Bindungselementen: Protokollbindungselemente, Codierungsbindungselemente und Transportbindungselemente.  
  
 Protokollbindungselemente &#8211; Diese Elemente stellen für Nachrichten ausgeführte Verarbeitungsschritte auf höherer Ebene dar. Die von diesen Bindungselementen erstellten Kanäle und Listener können den Nachrichteninhalt hinzufügen, entfernen oder ändern. Eine gegebene Bindung verfügt möglicherweise über eine beliebige Anzahl von Protokollbindungselementen, die alle von <xref:System.ServiceModel.Channels.BindingElement> erben. Windows Communication Foundation (WCF) umfasst mehrere Protokoll Bindungs Elemente, einschließlich <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> und <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> .  
  
 Codierungsbindungselemente &#8211; Diese Elemente stellen eine Transformation zwischen einer Nachricht und einer Codierung dar, die für die Weiterleitung im Netz bereit ist. Typische WCF-Bindungen umfassen genau ein Codierungs Bindungs Element. Beispiele für Codierungsbindungselemente sind <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. Wird für eine Bindung kein Codierungsbindungselement angegeben, wird eine Standardcodierung verwendet. Wenn als Transport HTTP verwendet wird, ist dieser Standard Text, andernfalls binär.  
  
 Transportbindungselemente &#8211; Diese Elemente stellen die Übertragung einer codierten Nachricht über ein Transportprotokoll dar. Typische WCF-Bindungen umfassen genau ein Transport Bindungs Element, das von erbt <xref:System.ServiceModel.Channels.TransportBindingElement> . Beispiele für Transportbindungselemente sind <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> und <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>.  
  
 Bei der Erstellung neuer Bindungen ist die Reihenfolge der hinzugefügten Bindungselemente wichtig. Fügen Sie Bindungselemente immer in der folgenden Reihenfolge hinzu:  
  
|Ebene|Tastatur|Erforderlich|  
|-----------|-------------|--------------|  
|Transaktionsfluss|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=nameWithType>|Nein|  
|Zuverlässigkeit|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType>|Nein|  
|Sicherheit|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|Nein |  
|Composite Duplex|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=nameWithType>|Nein|  
|Codierung|Text, Binärdatei, MTOM, benutzerdefiniert|Ja\*|  
|Transport|TCP, Named Pipes, HTTP, HTTPS, MSMQ, benutzerdefiniert|Ja|  
  
\*Da für jede Bindung eine Codierung erforderlich ist, fügt WCF, wenn keine Codierung angegeben ist, eine Standard Codierung für Sie hinzu. Der Standard ist Text/XML für die HTTP- und HTTPS-Transporte, andernfalls binär.  
  
## <a name="creating-a-new-binding-element"></a>Erstellen eines neuen Bindungselements  

 Zusätzlich zu den von abgeleiteten Typen, die <xref:System.ServiceModel.Channels.BindingElement> von WCF bereitgestellt werden, können Sie eigene Bindungs Elemente erstellen. Dadurch können Sie bestimmen, wie der Bindungsstapel und die Komponenten erstellt werden, die in die Erstellung Ihres eigenen <xref:System.ServiceModel.Channels.BindingElement> eingehen, das sich mit den anderen vom System bereitgestellten Typen auf dem Stapel kombinieren lässt.  
  
 Wenn Sie beispielsweise ein `LoggingBindingElement` implementieren, das Nachrichten in einer Datenbank protokollieren kann, müssen Sie es im Kanalstapel oberhalb eines Transportkanals platzieren. In diesem Fall erstellt die Anwendung eine benutzerdefinierte Bindung, die, wie im folgenden Beispiel, das `LoggingBindingElement` mit dem `TcpTransportBindingElement` kombiniert.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),
  new TcpTransportBindingElement()  
);  
```  
  
 Wie Sie Ihr neues Bindungselement schreiben, hängt von seiner genauen Funktionalität ab. Eines der Beispiele, [Transport: UDP](../samples/transport-udp.md), bietet eine ausführliche Beschreibung, wie eine Art von Bindungs Element implementiert wird.  
  
## <a name="creating-a-new-binding"></a>Erstellen einer neuen Bindung  

 Ein benutzerdefiniertes Bindungselement kann auf zwei Weisen verwendet werden. Im vorherigen Abschnitt wurde die erste beschrieben: durch eine benutzerdefinierte Bindung. Benutzerdefinierte Bindungen erlauben Benutzern, basierend auf einer beliebigen Gruppe von Bindungselementen einschließlich solcher, die von Benutzern erstellt wurden, eigene Bindungen zu definieren.  
  
 Wenn Sie die Bindung in mehr als einer Anwendung einsetzen, erstellen Sie die eigene Bindung und erweitern die <xref:System.ServiceModel.Channels.Binding>. Dadurch ist es nicht mehr notwendig, jedes Mal, wenn Sie sie verwenden möchten, manuell eine benutzerdefinierte Bindung zu erstellen. Eine benutzerdefinierte Bindung ermöglicht es Ihnen, das Verhalten der Bindung einschließlich benutzerdefinierter Bindungselemente zu definieren. Und es ist *vorab gepackt*: Sie müssen die Bindung nicht jedes Mal neu erstellen, wenn Sie Sie verwenden.  
  
 Eine benutzerdefinierte Bindung muss zumindest die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode und die <xref:System.ServiceModel.Channels.Binding.Scheme%2A>-Eigenschaft implementieren.  
  
 Die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode gibt eine neue <xref:System.ServiceModel.Channels.BindingElementCollection> zurück, die die Bindungselemente für die Bindung enthält. Die Auflistung ist sortiert, wobei die Protokollbindungselemente an erster Stelle stehen sollten, gefolgt von dem Codierungsbindungselement und dem Transportbindungselement. Wenn Sie die von einem System bereitgestellten Bindungs Elemente des WCF-Systems verwenden, müssen Sie die in [benutzerdefinierten Bindungen](custom-bindings.md)angegebenen Regeln für die Bindungs Element Anordnung befolgen. Diese Auflistung sollte niemals auf Objekte verweisen, auf die innerhalb der benutzerdefinierten Bindungsklasse verwiesen wird. Daraus folgt, dass Autoren von Bindungen einen `Clone()` der <xref:System.ServiceModel.Channels.BindingElementCollection> bei jedem Aufruf von <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> zurückgeben müssen.  
  
 Die <xref:System.ServiceModel.Channels.Binding.Scheme%2A>-Eigenschaft stellt das URI-Schema für das in der Bindung verwendete Transportprotokoll dar. Beispielsweise geben *WSHttpBinding* und *NetTcpBinding* "http" und "net. TCP" von ihren jeweiligen <xref:System.ServiceModel.Channels.Binding.Scheme%2A> Eigenschaften zurück.  
  
 Eine vollständige Liste optionaler Methoden und Eigenschaften für benutzerdefinierte Bindungselemente finden Sie unter <xref:System.ServiceModel.Channels.Binding>.  
  
### <a name="example"></a>Beispiel  

 In diesem Beispiel wird Profilbindung in `SampleProfileUdpBinding` implementiert, das von <xref:System.ServiceModel.Channels.Binding> abgeleitet wird. Die `SampleProfileUdpBinding` enthält bis zu vier Bindungs Elemente, die von einem Benutzer erstellt wurden, `UdpTransportBindingElement` und drei vom System bereitgestellte: `TextMessageEncodingBindingElement` , `CompositeDuplexBindingElement` und `ReliableSessionBindingElement` .  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
## <a name="security-restrictions-with-duplex-contracts"></a>Sicherheitseinschränkungen bei Duplexverträgen  

 Nicht alle Bindungselemente sind miteinander kompatibel. Es gibt insbesondere einige Einschränkungen für Sicherheitsbindungselemente, wenn sie mit Duplexverträgen verwendet werden.  
  
### <a name="one-shot-security"></a>One-Shot-Sicherheit  

 Sie können "One-Shot"-Sicherheit implementieren, bei der alle erforderlichen Sicherheits Anmelde Informationen in einer einzelnen Nachricht gesendet werden, indem Sie das- `negotiateServiceCredential` Attribut des- \<message> Konfigurations Elements auf festlegen `false` .  
  
 Die "One-Shot"-Authentifizierung funktioniert nicht mit Duplexverträgen.  
  
 Bei Anforderung-Antwort-Verträgen funktioniert die "One-Shot"-Authentifizierung nur, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>-Instanzen unterstützt.  
  
 Bei unidirektionalen Verträgen funktioniert die „One-Shot“-Authentifizierung, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>-, <xref:System.ServiceModel.Channels.IRequestSessionChannel>-, <xref:System.ServiceModel.Channels.IOutputChannel>- oder <xref:System.ServiceModel.Channels.IOutputSessionChannel>-Instanzen unterstützt.  
  
### <a name="cookie-mode-security-context-tokens"></a>Cookie-Modus-Sicherheitskontexttoken  

 Cookie-Modus-Sicherheitskontexttoken können nicht mit Duplexverträgen verwendet werden.  
  
 Bei Anforderung-Antwort-Verträgen funktionieren Cookie-Modus-Sicherheitskontexttoken nur, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>-Instanzen unterstützt.  
  
 Bei unidirektionalen Verträgen funktionieren Cookie-Modus-Sicherheitskontexttoken, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>-Instanzen unterstützt.  
  
### <a name="session-mode-security-context-tokens"></a>Sitzungsmodus-Sicherheitskontexttoken  

 Ein Sitzungsmodus-SCT funktioniert für Duplexverträge, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IDuplexChannel>- oder <xref:System.ServiceModel.Channels.IDuplexSessionChannel>-Instanzen unterstützt.  
  
 Ein Sitzungsmodus-SCT funktioniert für Anforderung-Antwort-Verträge, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IDuplexChannel>-, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>-, <xref:System.ServiceModel.Channels.IRequestChannel>- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>-Instanzen unterstützt.  
  
 Ein Sitzungsmodus-SCT funktioniert für unidirektionale Verträge, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IDuplexChannel>-, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>-, <xref:System.ServiceModel.Channels.IRequestChannel>- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>-Instanzen unterstützt.  
  
## <a name="deriving-from-a-standard-binding"></a>Ableiten von einer Standardbindung  

 Statt eine völlig neue Bindungsklasse zu erstellen, ist es möglich, eine vorhandene, vom System bereitgestellte Bindung zu erweitern. Ähnlich wie im vorangegangenen Fall müssen Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode und die <xref:System.ServiceModel.Channels.Binding.Scheme%2A>-Eigenschaft überschreiben.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.Binding>
- [Benutzerdefinierte Bindungen](custom-bindings.md)
