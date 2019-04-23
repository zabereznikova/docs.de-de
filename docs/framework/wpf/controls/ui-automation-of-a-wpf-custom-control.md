---
title: Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: 0d663acc195b36fdc95c196f2233ae997fbd9195
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132768"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] stellt eine einzelne allgemeine Schnittstelle bereit, die Automatisierungsclients zum Untersuchen oder Ausführen der Benutzerschnittstellen in unterschiedlichen Plattformen und Frameworks verwenden können. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es jeweils Qualitätssicherungcode (Testcode) und Barrierefreiheitsanwendungen, z.B. die Sprachausgabe, Benutzerschnittstellenelemente zu untersuchen und Benutzerzugriff mit ihnen aus anderem Code zu simulieren. Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] für alle Plattformen finden Sie unter „Barrierefreiheit“.  
  
 In diesem Thema wird beschrieben, wie ein serverseitiger Benutzeroberflächenautomatisierungs-Anbieter, der in einer WPF-Anwendung ausgeführt wird, für ein benutzerdefiniertes Steuerelement implementiert wird. WPF unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peer-Automatisierungsobjekten, die zur Struktur der Elemente der Benutzeroberfläche parallel ist. Testcode und -anwendungen, die Barrierefreiheitsfunktionen bereitstellen, können Automatisierungspeerobjekte direkt (für Code, der gerade ausgeführt wird) oder über eine allgemeine Schnittstelle verwenden, die von [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] bereitgestellt wird.  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Automatisierungspeerklassen  
 WPF-Steuerelemente unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peerklassen, die abgeleitet <xref:System.Windows.Automation.Peers.AutomationPeer>. Gemäß der Konvention beginnen Namen von Peerklassen mit dem Klassennamen des Steuerelements und enden mit „AutomationPeer“. Z. B. <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> ist die Peerklasse für den <xref:System.Windows.Controls.Button> -Klasse. Die Peerklassen entsprechen weitgehend den [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Steuerelementtypen, gelten jedoch spezifisch für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente. Automatisierungscode der auf WPF-Anwendungen über die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Schnittstelle zugreift, verwendet keine Automatisierungspeers direkt, jedoch kann der Automatisierungscode im selben Prozessbereich Automatisierungspeers direkt verwenden.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Integrierte Automatisierungspeerklassen  
 Elemente implementieren eine Automatisierungspeerklasse, wenn sie Schnittstellenaktivität vom Benutzer akzeptieren oder Informationen enthalten, die von Benutzern von Anwendungen der Sprachausgabe benötigt werden. Nicht alle visuellen WPF-Elemente verfügen über Automatisierungspeers. Beispiele für Klassen, die Automatisierungspeers implementieren sind <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, und <xref:System.Windows.Controls.Label>. Beispiele für Klassen, die keine Automatisierungspeers implementieren sind abgeleitete Klassen <xref:System.Windows.Controls.Decorator>, z. B. <xref:System.Windows.Controls.Border>, und Klassen, die basierend auf <xref:System.Windows.Controls.Panel>, z. B. <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Canvas>.  
  
 Die Basis <xref:System.Windows.Controls.Control> Klasse besitzt keine entsprechende Peerklasse. Wenn Sie eine Peerklasse benötigen, um ein benutzerdefiniertes Steuerelement entsprechen, die abgeleitet <xref:System.Windows.Controls.Control>, sollten Sie die benutzerdefinierte Peerklasse von ableiten <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Sicherheitsüberlegungen zu abgeleiteten Peers  
 Automatisierungspeers müssen in einer Teilausführungsumgebung ausgeführt werden. Code in der UIAutomationClient-Assembly ist nicht konfiguriert, in einer teilweise vertrauenswürdigen Umgebung ausgeführt zu werden, und Automatisierungspeercode sollte nicht auf diese Assembly verweisen. Stattdessen sollten Sie diese Klassen in der UIAutomationTypes-Assembly verwenden. Sie sollten z. B. Verwenden der <xref:System.Windows.Automation.AutomationElementIdentifiers> Klasse vom UIAutomationTypes-Assembly, die entspricht der <xref:System.Windows.Automation.AutomationElement> Klasse in der UIAutomationClient-Assembly. Es ist sicher, auf die UIAutomationTypes-Assembly in Automatisierungspeercode zu verweisen.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Peernavigation  
 Nach dem Suchen nach einem Automatisierungspeer, kann in-Process-Code die Peerstruktur navigieren, durch den Aufruf des Objekts <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> Methoden. Navigation zwischen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Elemente in einem Steuerelement wird von der Peer Implementierung von unterstützt die <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> Methode. Das Benutzeroberflächenautomatisierungssystem ruft diese Methode auf, um eine Struktur von Unterelementen zu erstellen, die in einem Steuerelement vorhanden sind, z.B. Listenelemente in einem Listenfeld. Der Standardwert <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> Methode durchläuft die visuelle Struktur von Elementen, die die Struktur für Automatisierungspeers zu erstellen. Benutzerdefinierte Steuerelemente überschreiben diese Methode, um untergeordnete Elemente für Automatisierungsclients verfügbar zu machen, dabei werden die Automatisierungspeers von Elementen zurückgegeben, die Informationen ausdrücken oder Benutzerinteraktion erlauben.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Anpassungen in einem abgeleiteten Peer  
 Alle Klassen, die abgeleitet <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> enthalten die geschützte virtuelle Methode <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF ruft <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> um das Automatisierungspeerobjekt für jedes Steuerelement zu erhalten. Automatisierungscode kann Peers zum Abrufen von Informationen über Merkmale und Funktionen des Steuerelements verwenden und um interaktive Verwendung zu simulieren. Ein benutzerdefiniertes Steuerelement, das Automatisierung unterstützt außer Kraft setzen muss <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> und zurückgeben eine Instanz einer Klasse, die von abgeleitet <xref:System.Windows.Automation.Peers.AutomationPeer>. Angenommen, ein benutzerdefiniertes Steuerelement abgeleitet der <xref:System.Windows.Controls.Primitives.ButtonBase> -Klasse, und klicken Sie dann auf das von zurückgegebene Objekt <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> ableiten sollten <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Wenn Sie ein benutzerdefiniertes Steuerelement implementieren, müssen Sie die „Kernmethoden“ der grundlegenden Automatisierungspeerklasse außer Kraft setzen, die das Verhalten eindeutig beschreiben und für Ihr benutzerdefiniertes Steuerelement spezifisch sind.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer außer Kraft setzen  
 Überschreiben der <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> -Methode für das benutzerdefinierte Steuerelement so, dass die It Ihr Anbieterobjekt zurückgibt, die direkt oder indirekt von abgeleitet werden müssen <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>GetPattern außer Kraft setzen  
 Automatisierungspeers vereinfachen zwar manche technischen Aspekte der Implementierung von serverseitigen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Anbietern, aber Automatisierungspeers von benutzerdefinierten Steuerelementen müssen dennoch Musterschnittstellen behandeln. Wie nicht-WPF-Anbieter, Peers Unterstützung von Steuerelementmustern durch die Bereitstellung von Implementierungen der Schnittstellen in den <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> -Namespace, z. B. <xref:System.Windows.Automation.Provider.IInvokeProvider>. Die Schnittstellen der Steuerelementmuster können entweder vom Peer selbst, oder von einem anderen Objekt implementiert werden. Die Peer Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> gibt das Objekt, das das angegebene Muster unterstützt. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Code ruft die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode und gibt eine <xref:System.Windows.Automation.Peers.PatternInterface> Enumerationswert. Ihre Überschreibung der <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> sollte das Objekt zurück, das das angegebene Muster implementiert. Wenn das Steuerelement nicht über eine benutzerdefinierte Implementierung eines Musters verfügt, können Sie die Implementierung des Basistyps aufrufen <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> um entweder dessen Implementierung oder Null abzurufen, wenn das Muster für diesen Steuerelementtyp nicht unterstützt wird. Z. B. ein benutzerdefiniertes NumericUpDown-Steuerelement kann auf einen Wert innerhalb eines Bereichs festgelegt werden damit die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Peer implementieren würde die <xref:System.Windows.Automation.Provider.IRangeValueProvider> Schnittstelle. Das folgende Beispiel zeigt wie der Peers <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode wird überschrieben, zum Antworten auf eine <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> Wert.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Ein <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> -Methode kann auch ein Unterelement als den Musteranbieter angeben. Der folgende code zeigt, wie <xref:System.Windows.Controls.ItemsControl> Übertragungen Scrollen Muster behandeln, die dem Peer, der internen <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
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
  
 Zum Angeben eines Unterelements für Musterbehandlung dieser Code Ruft das untergeordnete Objekt ab, erstellt einen Peer mit der <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> -Methode legt die <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> Eigenschaft des neuen Peers auf den aktuellen Peer, und gibt den neuen Peer zurück. Festlegen von <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> auf einem Unterelement wird verhindert, dass das Unterelement in der Peerstruktur angezeigt werden und bezieht sich auf alle durch das Unterelement ausgelösten Ereignisse als stammen aus dem Steuerelement im angegebenen <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. Die <xref:System.Windows.Controls.ScrollViewer> Steuerelement in der Automatisierungsstruktur nicht angezeigt, und die Bildlauf-Ereignisse, die es generiert angezeigt werden, stammen aus der <xref:System.Windows.Controls.ItemsControl> Objekt.  
  
### <a name="override-core-methods"></a>„Kern“-Methode außer Kraft setzen  
 Der Automatisierungscode ruft Informationen über Ihr Steuerelement ab, indem er die öffentlichen Methoden der Peer-Klasse aufruft. Um Informationen über Ihr Steuerelement bereitzustellen, setzen Sie jede Methode außer Kraft, deren Name mit „Core“ endet, falls die Implementierung Ihrer Steuerelemente sich von der Implementierung unterscheidet, die von der Basis-Automatisierungspeerklasse bereitgestellt wird. Mindestens ein Steuerelement implementieren muss die <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> Methoden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Die Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> beschreibt das Steuerelement durch die Rückgabe einer <xref:System.Windows.Automation.ControlType> Wert. Sie haben zwar zurückzugeben <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, Sie sollten einen spezifischeren Steuerelementtyp zurückgeben, wenn sie Ihr Steuerelement genau beschreibt. Der Rückgabewert <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> erfordert zusätzliche Arbeit für den Anbieter implementiert [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], und [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Clientprodukte der Steuerelementstruktur, Tastaturinteraktion und mögliche Steuerelementmuster vorhersehen.  
  
 Implementieren der <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methoden, um anzugeben, ob Ihr Steuerelement Dateninhalte enthält oder der eine interaktive Rolle in der Benutzeroberfläche (oder beides). Standardmäßig geben die beiden Methoden `true` zurück. Diese Einstellungen verbessern die Nutzbarkeit der Automatisierungstools, wie z.B. Sprachausgabe-Tools, die mit diesen Methoden die Automatisierungsstruktur filtern. Wenn Ihre <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Übertragungen Muster Peer eines Unterelements, den Unterelementen-Peer Ausnahmebehandlung <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode zurückgeben "false", um den Unterelementen-Peer aus der Automatisierungsstruktur auszublenden. Z. B. ein Bildlauf eine <xref:System.Windows.Controls.ListBox> erfolgt durch eine <xref:System.Windows.Controls.ScrollViewer>, und der Automatisierungspeer für <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> wird zurückgegeben, indem Sie die <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> -Methode der der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> zugeordnete der <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Aus diesem Grund die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> gibt `false`, sodass die <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> wird in der Automatisierungsstruktur nicht angezeigt.  
  
 Ihr Automatisierungspeer sollte dem Steuerelement entsprechende Standardwerte bereitstellen. Beachten Sie, dass XAML, die das Steuerelement verweist auf Ihre Peer-Implementierungen der wichtigsten Methoden, dazu überschreiben kann <xref:System.Windows.Automation.AutomationProperties> Attribute. Der folgende XAML-Code erstellt z.B. eine Schaltfläche mit zwei benutzerdefinierten [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Eigenschaften.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementieren von Musteranbietern  
 Die von einem benutzerdefinierten Anbieter implementierten Schnittstellen werden explizit deklariert werden, wenn das besitzende Element direkt abgeleitet <xref:System.Windows.Controls.Control>. Der folgende Code deklariert beispielsweise einen Peer für ein <xref:System.Windows.Controls.Control> , das einen Bereichswert implementiert.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Wenn das besitzende Steuerelement wie z. B. von einer bestimmten Art von Steuerelement abgeleitet wird <xref:System.Windows.Controls.Primitives.RangeBase>, der Peer kann von einem Peer-Klasse abgeleitet werden. In diesem Fall wäre der Peer leiten Sie von <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, der eine grundlegende Implementierung der bereitstellt <xref:System.Windows.Automation.Provider.IRangeValueProvider>. Der folgende Code veranschaulicht die Deklaration eines solchen Peers.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Ein Beispielimplementierung finden Sie unter [NumericUpDown Custom Control with Theme and UI Automation Support Sample](https://go.microsoft.com/fwlink/?LinkID=160025) (benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung).  
  
### <a name="raise-events"></a>Auslösen von Ereignissen  
 Automatisierungsclients können Automatisierungsereignisse abonnieren. Benutzerdefinierte Steuerelemente müssen Änderungen durch den Aufruf Steuerelementzustände melden die <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> Methode. Auf ähnliche Weise aufrufen, wenn sich ein Eigenschaftswert ändert, die <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> Methode. Der folgende Code zeigt, wie Sie das Peerobjekt aus dem Steuerelementcode abrufen und eine Methode zum Auslösen eines Ereignisses aufrufen. Als Optimierung überprüft der Code, ob Listener für diesen Ereignistyp vorhanden sind. Ereignisse werden nur dann ausgelöst, wenn Listener vorhanden sind, sodass unnötiger Aufwand vermieden wird und das Steuerelement reaktionsfähig bleibt.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierung](../../ui-automation/ui-automation-overview.md)
- [NumericUpDown Custom Control with Theme and UI Automation Support Sample](https://go.microsoft.com/fwlink/?LinkID=160025)
- [Server-Side UI Automation Provider Implementation](../../ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
