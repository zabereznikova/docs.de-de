---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating custom bindings
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
ms.openlocfilehash: 9aaaf6a10e0c51db35720d72512c1a91cfbb9720
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256741"
---
# <a name="how-to-create-a-custom-binding-using-the-securitybindingelement"></a>Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement

Windows Communication Foundation (WCF) umfasst mehrere vom System bereitgestellte Bindungen, die konfiguriert werden können, aber nicht vollständig flexibel sind, wenn alle Sicherheitsoptionen konfiguriert werden, die von WCF unterstützt werden. Dieses Thema veranschaulicht, wie eine benutzerdefinierte Bindung direkt aus individuellen Bindungselementen erstellt wird, und stellt einige der Sicherheitseinstellungen heraus, die bei der Erstellung einer derartigen Bindung festgelegt werden können. Weitere Informationen zum Erstellen von benutzerdefinierten Bindungen finden Sie unter [Erweitern von Bindungen](../extending/extending-bindings.md).  
  
> [!WARNING]
> <xref:System.ServiceModel.Channels.SecurityBindingElement> unterstützt die <xref:System.ServiceModel.Channels.IDuplexSessionChannel>-Kanalform nicht, die der standardmäßig vom TCP-Transport verwendeten Kanalform entspricht, wenn <xref:System.ServiceModel.TransferMode> auf <xref:System.ServiceModel.TransferMode.Buffered> festgelegt ist. Sie müssen <xref:System.ServiceModel.TransferMode> auf <xref:System.ServiceModel.TransferMode.Streamed> festlegen, um <xref:System.ServiceModel.Channels.SecurityBindingElement> in diesem Szenario verwenden.  
  
## <a name="creating-a-custom-binding"></a>Erstellen einer benutzerdefinierten Bindung  

 In WCF bestehen alle Bindungen aus *Bindungs Elementen*. Jedes Bindungselement wird von der <xref:System.ServiceModel.Channels.BindingElement>-Klasse abgeleitet. Bei den standardmäßigen, vom System bereitgestellten Bindungen werden die Bindungselemente für Sie erstellt und konfiguriert, einige der Eigenschaftseinstellungen können jedoch angepasst werden.  
  
 Im Gegensatz dazu werden zum Erstellen einer benutzerdefinierten Bindung Bindungselemente erstellt und konfiguriert, und aus den Bindungselementen wird eine <xref:System.ServiceModel.Channels.CustomBinding> erstellt.  
  
 Fügen Sie hierzu die einzelnen Bindungselemente einer Auflistung hinzu, die durch eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse repräsentiert wird, und legen Sie anschließend die `Elements`-Eigenschaft der `CustomBinding` auf dieses Objekt fest. Die Bindungselemente müssen in der folgenden Reihenfolge hinzugefügt werden: Transaktionsfluss, zuverlässige Sitzung, Sicherheit, Composite Duplex, Unidirektional, Streamsicherheit, Nachrichtencodierung und Transport. Beachten Sie, dass nicht alle aufgelisteten Bindungselemente in jeder Bindung erforderlich sind.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  

 Drei Bindungselemente beziehen sich auf die Sicherheit auf Nachrichtenebene, wobei alle von der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse abgeleitet werden. Die drei sind <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Das <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> wird für Sicherheit im gemischten Modus verwendet. Die anderen beiden Elemente werden verwendet, wenn die Nachrichtenebene Sicherheit bereitstellt.  
  
 Zusätzliche Klassen werden verwendet, wenn Sicherheit auf Transportebene bereitgestellt wird:  
  
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>Erforderliche Bindungselemente  

 Es gibt eine große Anzahl von möglichen Bindungselementen, die zu einer Bindung kombiniert werden können. Nicht alle Kombinationen sind zulässig. In diesem Abschnitt werden die für eine Sicherheitsbindung erforderlichen Elemente beschrieben.  
  
 Gültige Sicherheitsbindungen hängen von vielen Faktoren ab, unter anderem von folgenden:  
  
- Sicherheitsmodus  
  
- Transportprotokoll  
  
- Das im Vertrag angegebene Nachrichtenaustauschmuster (MEP)  
  
 Die folgende Tabelle enthält die gültigen Konfigurationen von Bindungselementstapeln für jede Kombination der oben genannten Faktoren. Beachten Sie, dass es sich herbei um Mindestanforderungen handelt. Sie können der Bindung weitere Bindungselemente hinzufügen (beispielsweise Elemente zur Nachrichtencodierung, Transaktionsbindungselemente usw.).  
  
|Sicherheitsmodus|Transport|Nachrichtenaustauschmuster des Vertrags|Nachrichtenaustauschmuster des Vertrags|Nachrichtenaustauschmuster des Vertrags|  
|-------------------|---------------|---------------------------------------|---------------------------------------|---------------------------------------|  
|||`Datagram`|`Request Reply`|`Duplex`|  
|Transport|HTTPS||||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP||||  
|||OneWayBindingElement|||  
|||SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|`Message`|Http|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|  
|||||CompositeDuplexBindingElement|  
|||OneWayBindingElement||OneWayBindingElement|  
|||HttpTransportBindingElement|HttpTransportBindingElement|HttpTransportBindingElement|  
||TCP|SecurityBindingElement|SecurityBindingElement|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Gemischt (Transport mit Nachrichtenanmeldeinformationen)|HTTPS|TransportSecurityBindingElement|TransportSecurityBindingElement||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP|TransportSecurityBindingElement|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|SymmetricSecurityBindingElement (Authentifizierungsmodus = SecureConversation)|  
|||OneWayBindingElement|||  
|||SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|SSL oder Windows-StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
  
 Beachten Sie, dass für SecurityBindingElements eine Vielzahl konfigurierbarer Einstellungen zur Verfügung stehen. Weitere Informationen finden Sie unter [SecurityBindingElement-Authentifizierungs Modi](securitybindingelement-authentication-modes.md).  
  
 Weitere Informationen finden Sie unter [Sichere Konversationen und sichere Sitzungen](secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>So erstellen Sie eine benutzerdefinierte Bindung mit dem SymmetricSecurityBindingElement  
  
1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse mit dem Namen `outputBec`.  
  
2. Rufen Sie die statische `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`-Methode auf, durch die eine Instanz der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Klasse zurückgegeben wird.  
  
3. Fügen Sie das <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> zur Sammlung hinzu (`outputBec`), indem Sie die `Add`-Methode der <xref:System.Collections.ObjectModel.Collection%601> der <xref:System.ServiceModel.Channels.BindingElement>-Klasse aufrufen.  
  
4. Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>-Klasse, und fügen Sie diese der Sammlung hinzu (`outputBec`). Dies gibt die von der Bindung verwendete Codierung an.  
  
5. Erstellen Sie ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, und fügen Sie es der Sammlung hinzu (`outputBec`). Dadurch wird angegeben, dass die Bindung den HTTP-Transport nutzt.  
  
6. Erstellen Sie eine neue benutzerdefinierte Bindung, indem Sie eine Instanz der <xref:System.ServiceModel.Channels.CustomBinding>-Klasse erstellen und die Sammlung `outputBec` an den Konstruktor weitergeben.  
  
7. Die resultierenden benutzerdefinierten Bindungen teilen sich viele Eigenschaften mit dem Standard <xref:System.ServiceModel.WSHttpBinding>. Sicherheit wird auf Nachrichtenebene und Windows-Anmeldeinformationen festgelegt, aber sichere Sitzungen werden deaktiviert, eine Out-of-Band-Festlegung der Dienstanmeldeinformationen ist erforderlich und Signaturen werden nicht verschlüsselt. Die letzte kann nur durch Festlegen der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A>-Eigenschaft gesteuert werden, wie in Schritt 4 angezeigt. Die anderen beiden können über Einstellungen auf der Standardbindung kontrolliert werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  

 Das folgende Beispiel veranschaulicht eine vollständige Funktion zur Erstellung einer benutzerdefinierten Bindung, die ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> nutzt.  
  
### <a name="code"></a>Code  

 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Erweitern von Bindungen](../extending/extending-bindings.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
