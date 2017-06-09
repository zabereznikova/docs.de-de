---
title: "Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Sicherheit [WCF], zum Erstellen benutzerdefinierter Bindungen"
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] enthält diverse, vom System bereitgestellte und konfigurierbare Bindungen, die jedoch in Bezug auf die Konfiguration aller Optionen, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt, nicht die volle Flexibilität aufweisen. Dieses Thema veranschaulicht, wie eine benutzerdefinierte Bindung direkt aus individuellen Bindungselementen erstellt wird, und stellt einige der Sicherheitseinstellungen heraus, die bei der Erstellung einer derartigen Bindung festgelegt werden können. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erstellen von benutzerdefinierten Bindungen finden Sie unter [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
> [!WARNING]
>  <xref:System.ServiceModel.Channels.SecurityBindingElement> unterstützt nicht die <xref:System.ServiceModel.Channels.IDuplexSessionChannel> channel-Form, die die Verwendung für die Form von Kanal vom TCP ist beim transport <xref:System.ServiceModel.TransferMode> auf festgelegt ist <xref:System.ServiceModel.TransferMode.Buffered>. Sie müssen festlegen, <xref:System.ServiceModel.TransferMode> auf <xref:System.ServiceModel.TransferMode.Streamed> zur Verwendung <xref:System.ServiceModel.Channels.SecurityBindingElement> in diesem Szenario.  
  
## <a name="creating-a-custom-binding"></a>Erstellen einer benutzerdefinierten Bindung  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Alle Bindungen bestehen aus *Bindungselementen*. Jedes Bindungselement leitet sich von der <xref:System.ServiceModel.Channels.BindingElement> Klasse. Bei den standardmäßigen, vom System bereitgestellten Bindungen werden die Bindungselemente für Sie erstellt und konfiguriert, einige der Eigenschaftseinstellungen können jedoch angepasst werden.  
  
 Im Gegensatz dazu zum Erstellen einer benutzerdefinierten Bindung Bindungselemente erstellt und konfiguriert werden und ein <xref:System.ServiceModel.Channels.CustomBinding> aus den Bindungselementen erstellt wird.  
  
 Zu diesem Zweck fügen Sie die einzelnen Bindungselemente einer Auflistung dargestellt, die von einer Instanz von der <xref:System.ServiceModel.Channels.BindingElementCollection> Klasse, und legen Sie dann die `Elements` Eigenschaft der `CustomBinding` auf dieses Objekt. Die Bindungselemente müssen in der folgenden Reihenfolge hinzugefügt werden: Transaktionsfluss, zuverlässige Sitzung, Sicherheit, Composite Duplex, Unidirektional, Streamsicherheit, Nachrichtencodierung und Transport. Beachten Sie, dass nicht alle aufgelisteten Bindungselemente in jeder Bindung erforderlich sind.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  
 Drei Bindungselemente beziehen sich auf die Sicherheit auf Nachrichtenebene, leiten Sie die von der <xref:System.ServiceModel.Channels.SecurityBindingElement> Klasse. Die drei sind <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, und <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Die <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> wird verwendet, um die Sicherheit im gemischten Modus. Die anderen beiden Elemente werden verwendet, wenn die Nachrichtenebene Sicherheit bereitstellt.  
  
 Zusätzliche Klassen werden verwendet, wenn Sicherheit auf Transportebene bereitgestellt wird:  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>Erforderliche Bindungselemente  
 Es gibt eine große Anzahl von möglichen Bindungselementen, die zu einer Bindung kombiniert werden können. Nicht alle Kombinationen sind zulässig. In diesem Abschnitt werden die für eine Sicherheitsbindung erforderlichen Elemente beschrieben.  
  
 Gültige Sicherheitsbindungen hängen von vielen Faktoren ab, unter anderem von folgenden:  
  
-   Sicherheitsmodus  
  
-   Transportprotokoll  
  
-   Das im Vertrag angegebene Nachrichtenaustauschmuster (MEP)  
  
 Die folgende Tabelle enthält die gültigen Konfigurationen von Bindungselementstapeln für jede Kombination der oben genannten Faktoren. Beachten Sie, dass es sich herbei um Mindestanforderungen handelt. Sie können der Bindung weitere Bindungselemente (beispielsweise Elemente zur Nachrichtencodierung, Transaktionsbindungselemente usw.) hinzufügen.  
  
|Sicherheitsmodus|Transport|Nachrichtenaustauschmuster des Vertrags|Nachrichtenaustauschmuster des Vertrags|Nachrichtenaustauschmuster des Vertrags|  
|-------------------|---------------|---------------------------------------|---------------------------------------|---------------------------------------|  
|||`Datagram`|`Request Reply`|`Duplex`|  
|Transport|Https||||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP||||  
|||OneWayBindingElement|||  
|||SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Meldung|Http|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|  
|||||CompositeDuplexBindingElement|  
|||OneWayBindingElement||OneWayBindingElement|  
|||HttpTransportBindingElement|HttpTransportBindingElement|HttpTransportBindingElement|  
||TCP|SecurityBindingElement|SecurityBindingElement|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Gemischt (Transport mit Nachrichtenanmeldeinformationen)|Https|TransportSecurityBindingElement|TransportSecurityBindingElement||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP|TransportSecurityBindingElement|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|  
|||OneWayBindingElement|||  
|||SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
  
 Beachten Sie, dass für SecurityBindingElements eine Vielzahl konfigurierbarer Einstellungen zur Verfügung stehen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][SecurityBindingElement-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Sichere Konversationen und sichere Sitzungen](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>So erstellen Sie eine benutzerdefinierte Bindung mit dem SymmetricSecurityBindingElement  
  
1.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection> Klasse mit dem Namen `outputBec`.  
  
2.  Rufen Sie die statische Methode `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`, womit eine Instanz von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> Klasse.  
  
3.  Hinzufügen der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> der Auflistung (`outputBec`) durch Aufrufen der `Add` Methode der <xref:System.Collections.ObjectModel.Collection%601> von <xref:System.ServiceModel.Channels.BindingElement> Klasse.  
  
4.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> Klasse und fügen es der Auflistung hinzu (`outputBec`). Dies gibt die von der Bindung verwendete Codierung an.  
  
5.  Erstellen einer <xref:System.ServiceModel.Channels.HttpTransportBindingElement> und fügen es der Auflistung hinzu (`outputBec`). Dadurch wird angegeben, dass die Bindung den HTTP-Transport nutzt.  
  
6.  Erstellen Sie eine neue benutzerdefinierte Bindung durch Erstellen einer Instanz von der <xref:System.ServiceModel.Channels.CustomBinding> -Klasse, und übergeben die Auflistung `outputBec` an den Konstruktor.  
  
7.  Die resultierende benutzerdefinierte Bindungen teilen sich viele Eigenschaften, die als Standard <xref:System.ServiceModel.WSHttpBinding>. Sicherheit wird auf Nachrichtenebene und Windows-Anmeldeinformationen festgelegt, aber sichere Sitzungen werden deaktiviert, eine Out-of-Band-Festlegung der Dienstanmeldeinformationen ist erforderlich und Signaturen werden nicht verschlüsselt. Die letzte kann gesteuert werden, nur durch Festlegen der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A> -Eigenschaft wie in Schritt 4 angezeigt. Die anderen beiden können über Einstellungen auf der Standardbindung kontrolliert werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel veranschaulicht eine vollständige Funktion um eine benutzerdefinierte Bindung erstellen, verwendet eine <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
### <a name="code"></a>Code  
 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)