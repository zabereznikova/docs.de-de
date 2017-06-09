---
title: "Erstellen benutzerdefinierter Bindungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Benutzerdefinierte Bindungen [WCF]"
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Erstellen benutzerdefinierter Bindungen
Es gibt mehrere Möglichkeiten, Bindungen zu erstellen, die nicht vom System bereitgestellt werden:  
  
-   Erstellen Sie eine benutzerdefinierte Bindung auf Grundlage der <xref:System.ServiceModel.Channels.CustomBinding>\-Klasse, die einen Container darstellt, den Sie mit Bindungselementen füllen.  Die benutzerdefinierte Bindung wird dann einem Dienstendpunkt hinzugefügt.  Sie können die benutzerdefinierte Bindung entweder programmgesteuert oder in der Konfigurationsdatei einer Anwendung erstellen.  Um das Bindungselement aus einer Anwendungskonfigurationsdatei verwenden zu können, muss es <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> erweitern.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu benutzerdefinierten Bindungen finden Sie unter [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md) und <xref:System.ServiceModel.Channels.CustomBinding>.  
  
-   Sie können eine Klasse erstellen, die von einer Standardbindung abgeleitet ist.  Sie können beispielsweise eine Klasse von <xref:System.ServiceModel.WSHttpBinding> ableiten und die <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A>\-Methode überschreiben, um Bindungselemente abzurufen und ein benutzerdefiniertes Bindungselement einzufügen oder einen bestimmten Wert für die Sicherheit festzulegen.  
  
-   Sie können einen neuen <xref:System.ServiceModel.Channels.Binding>\-Typ erstellen, um die Bindungsimplementierung vollständig zu steuern.  
  
## Die Reihenfolge der Bindungselemente  
 Jedes Bindungselement stellt einen Verarbeitungsschritt beim Senden und Empfangen von Nachrichten dar.  Zur Laufzeit erstellen Bindungselemente die Kanäle und die Listener, die notwendig sind, um ausgehende und eingehende Kanalstapel zu erstellen.  
  
 Es gibt drei Haupttypen von Bindungselementen: Protokollbindungselemente, Codierungsbindungselemente und Transportbindungselemente.  
  
 Protokollbindungselemente &\#8211; Diese Elemente stellen für Nachrichten ausgeführte Verarbeitungsschritte auf höherer Ebene dar.  Die von diesen Bindungselementen erstellten Kanäle und Listener können den Nachrichteninhalt hinzufügen, entfernen oder ändern.  Eine gegebene Bindung verfügt möglicherweise über eine beliebige Anzahl von Protokollbindungselementen, die alle von <xref:System.ServiceModel.Channels.BindingElement> erben.  [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet mehrere Protokollbindungselemente, einschließlich dem <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> und dem <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
 Codierungsbindungselemente &\#8211; Diese Elemente stellen eine Transformation zwischen einer Nachricht und einer Codierung dar, die für die Weiterleitung im Netz bereit ist.  Typische [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungen umfassen genau ein Codierungsbindungselement.  Beispiele für Codierungsbindungselemente sind <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.  Wird für eine Bindung kein Codierungsbindungselement angegeben, wird eine Standardcodierung verwendet.  Wenn als Transport HTTP verwendet wird, ist dieser Standard Text, andernfalls binär.  
  
 Transportbindungselemente &\#8211; Diese Elemente stellen die Übertragung einer codierten Nachricht über ein Transportprotokoll dar.  Typische [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungen schließen genau ein Transportbindungselement ein, das von <xref:System.ServiceModel.Channels.TransportBindingElement> erbt.  Beispiele für Transportbindungselemente sind <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> und <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>.  
  
 Bei der Erstellung neuer Bindungen ist die Reihenfolge der hinzugefügten Bindungselemente wichtig.  Fügen Sie Bindungselemente immer in der folgenden Reihenfolge hinzu:  
  
|Ebene|Optionen|Erforderlich|  
|-----------|--------------|------------------|  
|Transaktionsfluss|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=fullName>|Nein|  
|Zuverlässigkeit|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=fullName>|Nein|  
|Sicherheit|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=fullName>|Nein|  
|Composite Duplex|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=fullName>|Nein|  
|Codierung|Text, Binärdatei, MTOM, benutzerdefiniert|Ja\*|  
|Transport|TCP, Named Pipes, HTTP, HTTPS, MSMQ, benutzerdefiniert|Ja|  
  
 \*Da für jede Bindung eine Codierung notwendig ist, fügt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine Standardcodierung für Sie hinzu, wenn keine Codierung festgelegt ist.  Der Standard ist Text\/XML für die HTTP\- und HTTPS\-Transporte, andernfalls binär.  
  
## Erstellen eines neuen Bindungselements  
 Zusätzlich zu den von <xref:System.ServiceModel.Channels.BindingElement> abgeleiteten Typen, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geboten werden, können Sie Ihre eigenen Bindungselemente erstellen.  Dadurch können Sie bestimmen, wie der Bindungsstapel und die Komponenten erstellt werden, die in die Erstellung Ihres eigenen <xref:System.ServiceModel.Channels.BindingElement> eingehen, das sich mit den anderen vom System bereitgestellten Typen auf dem Stapel kombinieren lässt.  
  
 Wenn Sie beispielsweise ein `LoggingBindingElement` implementieren, das Nachrichten in einer Datenbank protokollieren kann, müssen Sie es im Kanalstapel oberhalb eines Transportkanals platzieren.  In diesem Fall erstellt die Anwendung eine benutzerdefinierte Bindung, die, wie im folgenden Beispiel, das `LoggingBindingElement` mit dem `TcpTransportBindingElement` kombiniert.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),   
  new TcpTransportBindingElement()  
);  
```  
  
 Wie Sie Ihr neues Bindungselement schreiben, hängt von seiner genauen Funktionalität ab.  In einem der Beispiele unter [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) finden Sie eine ausführliche Beschreibung, wie eine bestimmte Art von Bindungselement implementiert wird.  
  
## Erstellen einer neuen Bindung  
 Ein benutzerdefiniertes Bindungselement kann auf zwei Weisen verwendet werden.  Im vorherigen Abschnitt wurde die erste beschrieben: durch eine benutzerdefinierte Bindung.  Benutzerdefinierte Bindungen erlauben Benutzern, basierend auf einer beliebigen Gruppe von Bindungselementen einschließlich solcher, die von Benutzern erstellt wurden, eigene Bindungen zu definieren.  
  
 Wenn Sie die Bindung in mehr als einer Anwendung einsetzen, dann erstellen Sie die eigene Bindung und erweitern die <xref:System.ServiceModel.Channels.Binding>.  Dadurch ist es nicht mehr notwendig, jedes Mal, wenn Sie sie verwenden möchten, manuell eine benutzerdefinierte Bindung zu erstellen.  Eine benutzerdefinierte Bindung ermöglicht es Ihnen, das Verhalten der Bindung einschließlich benutzerdefinierter Bindungselemente zu definieren.  Und sie ist *bereits gepackt*: Sie müssen nicht jedes Mal die Bindung neu erstellen, wenn Sie sie verwenden wollen.  
  
 Eine benutzerdefinierte Bindung muss zumindest die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>\-Methode und die <xref:System.ServiceModel.Channels.Binding.Scheme%2A>\-Eigenschaft implementieren.  
  
 Die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>\-Methode gibt eine neue <xref:System.ServiceModel.Channels.BindingElementCollection> zurück, die die Bindungselemente für die Bindung enthält.  Die Auflistung ist sortiert, wobei die Protokollbindungselemente an erster Stelle stehen sollten, gefolgt von dem Codierungsbindungselement und dem Transportbindungselement.  Wenn Sie die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Bindungselemente verwenden, müssen Sie die Sortierungsregeln für Bindungselemente einhalten, die unter [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md) angegeben sind.  Diese Auflistung sollte niemals auf Objekte verweisen, auf die innerhalb der benutzerdefinierten Bindungsklasse verwiesen wird. Daraus folgt, dass Autoren von Bindungen einen `Clone()` der <xref:System.ServiceModel.Channels.BindingElementCollection> bei jedem Aufruf von <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> zurückgeben müssen.  
  
 Die <xref:System.ServiceModel.Channels.Binding.Scheme%2A>\-Eigenschaft stellt das URI\-Schema für das in der Bindung verwendete Transportprotokoll dar.  Zum Beispiel geben *WSHttpBinding* und *NetTcpBinding* "http" und "net.tcp" von ihren jeweiligen <xref:System.ServiceModel.Channels.Binding.Scheme%2A>\-Eigenschaften zurück.  
  
 Eine vollständige Liste optionaler Methoden und Eigenschaften für benutzerdefinierte Bindungselemente finden Sie unter <xref:System.ServiceModel.Channels.Binding>.  
  
### Beispiel  
 In diesem Beispiel wird Profilbindung in `SampleProfileUdpBinding` implementiert, das von <xref:System.ServiceModel.Channels.Binding> abgeleitet wird.  `SampleProfileUdpBinding` enthält bis zu vier Bindungselemente: Ein benutzerdefiniertes `UdpTransportBindingElement` und drei vom System bereitgestellte: `TextMessageEncodingBindingElement`, `CompositeDuplexBindingElement` und `ReliableSessionBindingElement`.  
  
```  
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
  
## Sicherheitseinschränkungen bei Duplexverträgen  
 Nicht alle Bindungselemente sind miteinander kompatibel.  Es gibt insbesondere einige Einschränkungen für Sicherheitsbindungselemente, wenn sie mit Duplexverträgen verwendet werden.  
  
### One\-Shot\-Sicherheit  
 Sie können "One\-Shot"\-Sicherheit implementieren, bei der alle notwendigen Sicherheitsanmeldeinformationen in einer einzelnen Nachricht gesendet werden, indem Sie das `negotiateServiceCredential`\-Attribut des \<message\>\-Konfigurationselements auf `false` festlegen.  
  
 Die "One\-Shot"\-Authentifizierung funktioniert nicht mit Duplexverträgen.  
  
 Bei Anforderung\-Antwort\-Verträgen funktioniert die "One\-Shot"\-Authentifizierung nur, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>\- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>\-Instanzen unterstützt.  
  
 Bei unidirektionalen Verträgen funktioniert die "One\-Shot"\-Authentifizierung, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>\-, <xref:System.ServiceModel.Channels.IRequestSessionChannel>\-, <xref:System.ServiceModel.Channels.IOutputChannel>\- oder <xref:System.ServiceModel.Channels.IOutputSessionChannel>\-Instanzen unterstützt.  
  
### Cookie\-Modus\-Sicherheitskontexttoken  
 Cookie\-Modus\-Sicherheitskontexttoken können nicht mit Duplexverträgen verwendet werden.  
  
 Bei Anforderung\-Antwort\-Verträgen funktionieren Cookie\-Modus\-Sicherheitskontexttoken nur, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>\- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>\-Instanzen unterstützt.  
  
 Bei unidirektionalen Verträgen funktionieren Cookie\-Modus\-Sicherheitskontexttoken, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IRequestChannel>\- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>\-Instanzen unterstützt.  
  
### Sitzungsmodus\-Sicherheitskontexttoken  
 Ein Sitzungsmodus\-SCT funktioniert für Duplexverträge, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IDuplexChannel>\- oder <xref:System.ServiceModel.Channels.IDuplexSessionChannel>\-Instanzen unterstützt.  
  
 Ein Sitzungsmodus\-SCT funktioniert für Anforderung\-Antwort\-Verträge, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IDuplexChannel>\-, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>\-, <xref:System.ServiceModel.Channels.IRequestChannel>\- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>\-Instanzen unterstützt.  
  
 Ein Sitzungsmodus\-SCT funktioniert für unidirektionale Verträge, wenn der Bindungsstapel unter dem Sicherheitsbindungselement die Erstellung von <xref:System.ServiceModel.Channels.IDuplexChannel>\-, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>\-, <xref:System.ServiceModel.Channels.IRequestChannel>\- oder <xref:System.ServiceModel.Channels.IRequestSessionChannel>\-Instanzen unterstützt.  
  
## Ableiten von einer Standardbindung  
 Statt eine völlig neue Bindungsklasse zu erstellen, ist es möglich, eine vorhandene, vom System bereitgestellte Bindung zu erweitern.  Ähnlich wie im vorangegangenen Fall müssen Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>\-Methode und die <xref:System.ServiceModel.Channels.Binding.Scheme%2A>\-Eigenschaft überschreiben.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>   
 [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)