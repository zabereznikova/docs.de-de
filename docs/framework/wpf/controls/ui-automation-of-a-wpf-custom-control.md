---
title: "Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d10c11cfcacb435438695b0e76ee8982ba9ef24a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] stellt eine einzelne allgemeine Schnittstelle bereit, die Automatisierungsclients zum Untersuchen oder Ausführen der Benutzerschnittstellen in unterschiedlichen Plattformen und Frameworks verwenden können. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es jeweils Qualitätssicherungcode (Testcode) und Barrierefreiheitsanwendungen, z.B. die Sprachausgabe, Benutzerschnittstellenelemente zu untersuchen und Benutzerzugriff mit ihnen aus anderem Code zu simulieren. Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] für alle Plattformen finden Sie unter „Barrierefreiheit“.  
  
 In diesem Thema wird beschrieben, wie ein serverseitiger Benutzeroberflächenautomatisierungs-Anbieter, der in einer WPF-Anwendung ausgeführt wird, für ein benutzerdefiniertes Steuerelement implementiert wird. WPF unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peer-Automatisierungsobjekten, die zur Struktur der Elemente der Benutzeroberfläche parallel ist. Testcode und -anwendungen, die Barrierefreiheitsfunktionen bereitstellen, können Automatisierungspeerobjekte direkt (für Code, der gerade ausgeführt wird) oder über eine allgemeine Schnittstelle verwenden, die von [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] bereitgestellt wird.  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Automatisierungspeerklassen  
 WPF-Steuerelemente unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peerklassen, die Ableitung <xref:System.Windows.Automation.Peers.AutomationPeer>. Gemäß der Konvention beginnen Namen von Peerklassen mit dem Klassennamen des Steuerelements und enden mit „AutomationPeer“. Beispielsweise <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> ist die Peerklasse für die <xref:System.Windows.Controls.Button> -Klasse. Die Peerklassen entsprechen weitgehend den [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Steuerelementtypen, gelten jedoch spezifisch für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente. Automatisierungscode der auf WPF-Anwendungen über die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Schnittstelle zugreift, verwendet keine Automatisierungspeers direkt, jedoch kann der Automatisierungscode im selben Prozessbereich Automatisierungspeers direkt verwenden.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Integrierte Automatisierungspeerklassen  
 Elemente implementieren eine Automatisierungspeerklasse, wenn sie Schnittstellenaktivität vom Benutzer akzeptieren oder Informationen enthalten, die von Benutzern von Anwendungen der Sprachausgabe benötigt werden. Nicht alle visuellen WPF-Elemente verfügen über Automatisierungspeers. Beispiele für Klassen, die Automatisierungspeers zu implementieren sind <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, und <xref:System.Windows.Controls.Label>. Beispiele für Klassen, die keine Automatisierungspeers implementieren sind abgeleitete Klassen <xref:System.Windows.Controls.Decorator>, wie z. B. <xref:System.Windows.Controls.Border>, und Klassen, die auf der Grundlage <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Canvas>.  
  
 Die Basis <xref:System.Windows.Controls.Control> Klasse verfügt nicht über eine entsprechende Peerklasse. Wenn Sie eine Peerklasse benötigen, um ein benutzerdefiniertes Steuerelement entsprechen, die abgeleitet <xref:System.Windows.Controls.Control>, leiten Sie sollten den benutzerdefinierten PeerResolver-Klasse von <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Sicherheitsüberlegungen zu abgeleiteten Peers  
 Automatisierungspeers müssen in einer Teilausführungsumgebung ausgeführt werden. Code in der UIAutomationClient-Assembly ist nicht konfiguriert, in einer teilweise vertrauenswürdigen Umgebung ausgeführt zu werden, und Automatisierungspeercode sollte nicht auf diese Assembly verweisen. Stattdessen sollten Sie diese Klassen in der UIAutomationTypes-Assembly verwenden. Sie sollten z. B. Verwenden der <xref:System.Windows.Automation.AutomationElementIdentifiers> Klasse aus der UIAutomationTypes-Assembly, die entspricht der <xref:System.Windows.Automation.AutomationElement> Klasse in der UIAutomationClient-Assembly. Es ist sicher, auf die UIAutomationTypes-Assembly in Automatisierungspeercode zu verweisen.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Peernavigation  
 Nach der Suche nach einem Automatisierungspeer, in-Process-Code kann in der Peerstruktur navigieren durch Aufrufen des Objekts <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> Methoden. Navigation zwischen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Elemente in einem Steuerelement wird von der Peer-Implementierung von unterstützt die <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> Methode. Das Benutzeroberflächenautomatisierungssystem ruft diese Methode auf, um eine Struktur von Unterelementen zu erstellen, die in einem Steuerelement vorhanden sind, z.B. Listenelemente in einem Listenfeld. Die Standardeinstellung <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> Methode durchläuft die visuelle Struktur der Elemente, die die Struktur der Automatisierungspeers erstellen. Benutzerdefinierte Steuerelemente überschreiben diese Methode, um untergeordnete Elemente für Automatisierungsclients verfügbar zu machen, dabei werden die Automatisierungspeers von Elementen zurückgegeben, die Informationen ausdrücken oder Benutzerinteraktion erlauben.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Anpassungen in einem abgeleiteten Peer  
 Alle Klassen, die davon Herleiten <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> enthalten die geschützte virtuelle Methode <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF-Aufrufe <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> an der Peer-Automatisierungsobjekt für jedes Steuerelement abzurufen. Automatisierungscode kann Peers zum Abrufen von Informationen über Merkmale und Funktionen des Steuerelements verwenden und um interaktive Verwendung zu simulieren. Ein benutzerdefiniertes Steuerelement, die Automatisierung unterstützt außer Kraft setzen muss <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> und zurückgeben eine Instanz einer Klasse, die abgeleitet <xref:System.Windows.Automation.Peers.AutomationPeer>. Angenommen, ein benutzerdefiniertes Steuerelement abgeleitet der <xref:System.Windows.Controls.Primitives.ButtonBase> -Klasse, und klicken Sie dann auf das zurückgegebene Objekt <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> abgeleitet sollten <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Wenn Sie ein benutzerdefiniertes Steuerelement implementieren, müssen Sie die „Kernmethoden“ der grundlegenden Automatisierungspeerklasse außer Kraft setzen, die das Verhalten eindeutig beschreiben und für Ihr benutzerdefiniertes Steuerelement spezifisch sind.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer außer Kraft setzen  
 Überschreiben Sie die <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Methode für das benutzerdefinierte Steuerelement so, dass die It die Anbieterobjekt zurückgibt, die direkt oder indirekt von abgeleitet werden müssen <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>GetPattern außer Kraft setzen  
 Automatisierungspeers vereinfachen zwar manche technischen Aspekte der Implementierung von serverseitigen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Anbietern, aber Automatisierungspeers von benutzerdefinierten Steuerelementen müssen dennoch Musterschnittstellen behandeln. Wie nicht-WPF-Anbietern Peers Unterstützung von Steuerelementmustern durch die Bereitstellung von Implementierungen der Schnittstellen in den <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> Namespace, z. B. <xref:System.Windows.Automation.Provider.IInvokeProvider>. Die Schnittstellen der Steuerelementmuster können entweder vom Peer selbst, oder von einem anderen Objekt implementiert werden. Die Peer-Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> gibt das Objekt, das das angegebene Muster unterstützt. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]Code wird die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode und gibt eine <xref:System.Windows.Automation.Peers.PatternInterface> -Enumerationswert. Überschreiben der <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> sollte das Objekt, das das angegebene Muster implementiert zurückgeben. Wenn das Steuerelement nicht über eine benutzerdefinierte Implementierung eines Musters verfügt, können Sie Implementierung der Basistyp Aufrufen <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> dessen Implementierung oder die Null abgerufen, wenn das Muster für diesen Steuerelementtyp nicht unterstützt wird. Beispielsweise ein benutzerdefiniertes NumericUpDown-Steuerelement kann auf einen Wert innerhalb eines Bereichs festgelegt werden damit die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Peer würden implementieren die <xref:System.Windows.Automation.Provider.IRangeValueProvider> Schnittstelle. Das folgende Beispiel zeigt wie des Peers <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> -Methode überschrieben wird, zum Antworten auf eine <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> Wert.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Ein <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode kann auch ein Unterelement als Musteranbieter angeben. Der folgende code zeigt, wie <xref:System.Windows.Controls.ItemsControl> Übertragungen Scrollen Musterbehandlung für den Peer des internen <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 Um ein Unterelement für die Musterbehandlung von anzugeben, dieser Code ruft jedoch stattdessen das Unterelement ab, erstellt einen Peer mit dem <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> -Methode legt die <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> Eigenschaft des neuen Peers auf den aktuellen Peer und gibt den neuen Peer zurück. Festlegen von <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> für ein Unterelement verhindert, dass das Unterelement enthalten sind, in der Automatisierungsstruktur Peer und bezieht sich auf alle durch das Unterelement ausgelösten Ereignisse stammen aus dem Steuerelement im angegebenen <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. Die <xref:System.Windows.Controls.ScrollViewer> Steuerelement erscheint nicht in der Automatisierungsstruktur und Durchführen eines Bildlaufs Ereignisse, die sie generiert stammen scheinen die <xref:System.Windows.Controls.ItemsControl> Objekt.  
  
### <a name="override-core-methods"></a>„Kern“-Methode außer Kraft setzen  
 Der Automatisierungscode ruft Informationen über Ihr Steuerelement ab, indem er die öffentlichen Methoden der Peer-Klasse aufruft. Um Informationen über Ihr Steuerelement bereitzustellen, setzen Sie jede Methode außer Kraft, deren Name mit „Core“ endet, falls die Implementierung Ihrer Steuerelemente sich von der Implementierung unterscheidet, die von der Basis-Automatisierungspeerklasse bereitgestellt wird. Mindestens ein Steuerelement implementieren muss die <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> Methoden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Ihre Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> beschreibt das Steuerelement wird durch Zurückgeben einer <xref:System.Windows.Automation.ControlType> Wert. Obwohl Sie zurückkehren können <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, sollten Sie eine spezifischere Steuerelementtypen zurückgeben, wenn sie das Steuerelement genau beschreibt. Ein Rückgabewert von <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> bedeuten einen Mehraufwand für den Anbieter implementiert [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], und [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] cientprodukte können nicht auf die Kontrollstruktur Tastaturinteraktion und mögliche Steuerelementmuster erwarten.  
  
 Implementieren der <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methoden, um anzugeben, ob das Steuerelement Daten enthält, oder eine interaktive Rolle in der Benutzeroberfläche (oder beides) erfüllt. Standardmäßig geben die beiden Methoden `true` zurück. Diese Einstellungen verbessern die Nutzbarkeit der Automatisierungstools, wie z.B. Sprachausgabe-Tools, die mit diesen Methoden die Automatisierungsstruktur filtern. Wenn Ihre <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Methode Übertragungen Muster ein Unterelement, das Unterelement Peer des Peers Ausnahmebehandlung <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode kann auf Peer in der Automatisierungsstruktur ausblenden "false" zurückgeben. Z. B. Bildlauf in eine <xref:System.Windows.Controls.ListBox> erfolgt durch eine <xref:System.Windows.Controls.ScrollViewer>, und der Automatisierungspeer für <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> zurückgegebene der <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> , zugeordnet ist die <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Aus diesem Grund die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> gibt `false`, sodass die <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> erscheint nicht in der Automatisierungsstruktur.  
  
 Ihr Automatisierungspeer sollte dem Steuerelement entsprechende Standardwerte bereitstellen. Beachten Sie, dass XAML, das das Steuerelement verweist auf Ihre Implementierungen Peer Core Methoden, indem Sie einschließlich überschreiben kann <xref:System.Windows.Automation.AutomationProperties> Attribute. Der folgende XAML-Code erstellt z.B. eine Schaltfläche mit zwei benutzerdefinierten [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Eigenschaften.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementieren von Musteranbietern  
 Die von einem benutzerdefinierten Anbieter implementierten Schnittstellen werden explizit deklariert werden, wenn das besitzende Element direkt abgeleitet <xref:System.Windows.Controls.Control>. Der folgende Code deklariert z. B. einen Peer für einen <xref:System.Windows.Controls.Control> , der einen Bereichswert implementiert.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Wenn eine bestimmte Art von Steuerelement wie z. B. besitzenden Steuerelements abgeleitet <xref:System.Windows.Controls.Primitives.RangeBase>, der Peer kann von einer entsprechenden abgeleiteten Peerklasse abgeleitet werden. In diesem Fall würden die Peer von ableiten <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, die eine grundlegende Implementierung der ausgeben <xref:System.Windows.Automation.Provider.IRangeValueProvider>. Der folgende Code veranschaulicht die Deklaration eines solchen Peers.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Ein Beispielimplementierung finden Sie unter [NumericUpDown Custom Control with Theme and UI Automation Support Sample](http://go.microsoft.com/fwlink/?LinkID=160025) (benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung).  
  
### <a name="raise-events"></a>Auslösen von Ereignissen  
 Automatisierungsclients können Automatisierungsereignisse abonnieren. Benutzerdefinierte Steuerelemente müssen Änderungen an Zustand durch Aufrufen von Steuern melden die <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> Methode. Auf ähnliche Weise aufrufen, wenn sich ein Eigenschaftswert ändert, die <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> Methode. Der folgende Code zeigt, wie Sie das Peerobjekt aus dem Steuerelementcode abrufen und eine Methode zum Auslösen eines Ereignisses aufrufen. Als Optimierung überprüft der Code, ob Listener für diesen Ereignistyp vorhanden sind. Ereignisse werden nur dann ausgelöst, wenn Listener vorhanden sind, sodass unnötiger Aufwand vermieden wird und das Steuerelement reaktionsfähig bleibt.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../../docs/framework/ui-automation/ui-automation-overview.md)  
 [Benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung](http://go.microsoft.com/fwlink/?LinkID=160025)  
 [Server-Side UI Automation Provider Implementation](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
