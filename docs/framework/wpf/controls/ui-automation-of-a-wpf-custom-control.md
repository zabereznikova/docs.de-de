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
ms.openlocfilehash: ef045ffaac47c6cb196d821c25d96c4d2cd7bf88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254244"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] stellt eine einzelne allgemeine Schnittstelle bereit, die Automatisierungsclients zum Untersuchen oder Ausführen der Benutzerschnittstellen in unterschiedlichen Plattformen und Frameworks verwenden können. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es jeweils Qualitätssicherungcode (Testcode) und Barrierefreiheitsanwendungen, z.B. die Sprachausgabe, Benutzerschnittstellenelemente zu untersuchen und Benutzerzugriff mit ihnen aus anderem Code zu simulieren. Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] für alle Plattformen finden Sie unter „Barrierefreiheit“.  
  
 In diesem Thema wird beschrieben, wie ein serverseitiger Benutzeroberflächenautomatisierungs-Anbieter, der in einer WPF-Anwendung ausgeführt wird, für ein benutzerdefiniertes Steuerelement implementiert wird. WPF unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peer-Automatisierungsobjekten, die zur Struktur der Elemente der Benutzeroberfläche parallel ist. Testcode und -anwendungen, die Barrierefreiheitsfunktionen bereitstellen, können Automatisierungspeerobjekte direkt (für Code, der gerade ausgeführt wird) oder über eine allgemeine Schnittstelle verwenden, die von [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] bereitgestellt wird.  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Automatisierungspeerklassen  
 WPF-Steuer [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Elemente unterstützen über eine Struktur von Peer Klassen <xref:System.Windows.Automation.Peers.AutomationPeer>, die von abgeleitet werden. Gemäß der Konvention beginnen Namen von Peerklassen mit dem Klassennamen des Steuerelements und enden mit „AutomationPeer“. Beispielsweise <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> ist die Peer Klasse für die <xref:System.Windows.Controls.Button> Steuerelement Klasse. Die Peerklassen entsprechen weitgehend den [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Steuerelementtypen, gelten jedoch spezifisch für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente. Automatisierungscode der auf WPF-Anwendungen über die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Schnittstelle zugreift, verwendet keine Automatisierungspeers direkt, jedoch kann der Automatisierungscode im selben Prozessbereich Automatisierungspeers direkt verwenden.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Integrierte Automatisierungspeerklassen  
 Elemente implementieren eine Automatisierungspeerklasse, wenn sie Schnittstellenaktivität vom Benutzer akzeptieren oder Informationen enthalten, die von Benutzern von Anwendungen der Sprachausgabe benötigt werden. Nicht alle visuellen WPF-Elemente verfügen über Automatisierungspeers. Beispiele für Klassen, die Automatisierungs Peers implementieren <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>sind, <xref:System.Windows.Controls.Label>und. Beispiele für Klassen, die keine Automatisierungspeers implementieren, sind <xref:System.Windows.Controls.Decorator>Klassen, die <xref:System.Windows.Controls.Border>von abgeleitet werden, z. b. <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Canvas>Klassen, die auf <xref:System.Windows.Controls.Panel>basieren, z. b.  
  
 Die Basis <xref:System.Windows.Controls.Control> Klasse verfügt nicht über eine entsprechende Peer Klasse. Wenn Sie eine Peer Klasse benötigen, die einem benutzerdefinierten Steuerelement entspricht, <xref:System.Windows.Controls.Control>das von abgeleitet wird, sollten Sie die Benutzer <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>definierte Peer Klasse von ableiten.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Sicherheitsüberlegungen zu abgeleiteten Peers  
 Automatisierungspeers müssen in einer Teilausführungsumgebung ausgeführt werden. Code in der UIAutomationClient-Assembly ist nicht konfiguriert, in einer teilweise vertrauenswürdigen Umgebung ausgeführt zu werden, und Automatisierungspeercode sollte nicht auf diese Assembly verweisen. Stattdessen sollten Sie diese Klassen in der UIAutomationTypes-Assembly verwenden. Sie sollten z. b. die <xref:System.Windows.Automation.AutomationElementIdentifiers> -Klasse aus der UIAutomationTypes-Assembly verwenden, die <xref:System.Windows.Automation.AutomationElement> der-Klasse in der UIAutomationClient-Assembly entspricht. Es ist sicher, auf die UIAutomationTypes-Assembly in Automatisierungspeercode zu verweisen.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Peernavigation  
 Nach dem Auffinden eines Automatisierungspeer kann in-Process-Code durch Aufrufen der-Methode <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> der-Methode des-Objekts durch Aufrufen der-Methode Die Navigation [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] zwischen Elementen in einem-Steuerelement wird von der-Implementierung <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> der-Methode des Peers unterstützt. Das Benutzeroberflächenautomatisierungssystem ruft diese Methode auf, um eine Struktur von Unterelementen zu erstellen, die in einem Steuerelement vorhanden sind, z.B. Listenelemente in einem Listenfeld. Die Standard <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> Methode durchläuft die visuelle Struktur der Elemente, um die Struktur von Automatisierungspeers zu erstellen. Benutzerdefinierte Steuerelemente überschreiben diese Methode, um untergeordnete Elemente für Automatisierungsclients verfügbar zu machen, dabei werden die Automatisierungspeers von Elementen zurückgegeben, die Informationen ausdrücken oder Benutzerinteraktion erlauben.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Anpassungen in einem abgeleiteten Peer  
 Alle Klassen, die von <xref:System.Windows.UIElement> abgeleitet <xref:System.Windows.ContentElement> werden und die geschützte virtuelle <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>Methode enthalten. WPF- <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Aufrufe, um das Automatisierungs Peer Objekt für jedes Steuerelement zu erhalten. Automatisierungscode kann Peers zum Abrufen von Informationen über Merkmale und Funktionen des Steuerelements verwenden und um interaktive Verwendung zu simulieren. Ein benutzerdefiniertes Steuerelement, das <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Automation unterstützt, muss eine Instanz einer von abgeleiteten <xref:System.Windows.Automation.Peers.AutomationPeer>Klasse überschreiben und zurückgeben. Wenn ein benutzerdefiniertes Steuerelement beispielsweise von <xref:System.Windows.Controls.Primitives.ButtonBase> der-Klasse abgeleitet ist, sollte <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> das von zurück <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>gegebene-Objekt von abgeleitet werden.  
  
 Wenn Sie ein benutzerdefiniertes Steuerelement implementieren, müssen Sie die „Kernmethoden“ der grundlegenden Automatisierungspeerklasse außer Kraft setzen, die das Verhalten eindeutig beschreiben und für Ihr benutzerdefiniertes Steuerelement spezifisch sind.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer außer Kraft setzen  
 Überschreiben <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Sie die-Methode für das benutzerdefinierte Steuerelement, sodass es das Anbieter Objekt zurückgibt, das <xref:System.Windows.Automation.Peers.AutomationPeer>direkt oder indirekt von abgeleitet werden muss.  
  
### <a name="override-getpattern"></a>GetPattern außer Kraft setzen  
 Automatisierungspeers vereinfachen zwar manche technischen Aspekte der Implementierung von serverseitigen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Anbietern, aber Automatisierungspeers von benutzerdefinierten Steuerelementen müssen dennoch Musterschnittstellen behandeln. Wie nicht-WPF-Anbieter unterstützen Peers Steuerelement Muster, indem Sie Implementierungen von <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> Schnittstellen im-Namespace bereitstellen, <xref:System.Windows.Automation.Provider.IInvokeProvider>z. b. Die Schnittstellen der Steuerelementmuster können entweder vom Peer selbst, oder von einem anderen Objekt implementiert werden. Die Peer-Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> gibt das Objekt zurück, das das angegebene Muster unterstützt. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]der Code ruft <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> die Methode auf und <xref:System.Windows.Automation.Peers.PatternInterface> gibt einen-Enumerationswert an. Die außer Kraft <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Setzung von sollte das Objekt zurückgeben, das das angegebene Muster implementiert. Wenn das Steuerelement keine benutzerdefinierte Implementierung eines Musters hat, können Sie die-Implementierung des <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Basistyps aufrufen, um entweder seine-Implementierung abzurufen, oder NULL, wenn das Muster für diesen Steuerelement Typen nicht unterstützt wird. Beispielsweise kann ein benutzerdefiniertes NumericUpDown-Steuerelement auf einen Wert innerhalb eines Bereichs festgelegt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] werden, sodass der <xref:System.Windows.Automation.Provider.IRangeValueProvider> Peer die-Schnittstelle implementieren würde. Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> -Methode des Peers überschrieben wird, <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> um auf einen-Wert zu reagieren.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Eine <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode kann auch ein Unterelement als Muster Anbieter angeben. Der folgende Code zeigt, <xref:System.Windows.Controls.ItemsControl> wie die Verarbeitung von scrollmustern an den Peer des <xref:System.Windows.Controls.ScrollViewer> internen Steuer Elements überträgt.  
  
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
  
 Um ein Unterelement für die Muster Behandlung anzugeben, ruft dieser Code das untergeordnete Objekt ab, erstellt mithilfe der <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> -Methode einen Peer, legt die <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> -Eigenschaft des neuen Peers auf den aktuellen Peer fest und gibt den neuen Peer zurück. Durch <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> Festlegen von für ein Unterelement wird verhindert, dass das Unterelement in der Automatisierungs Peer Struktur angezeigt wird, und es werden alle Ereignisse, die vom Unterelement ausgelöst werden, als <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>Ausgangswert aus dem in angegebenen Steuerelement festgelegt. Das <xref:System.Windows.Controls.ScrollViewer> -Steuerelement wird nicht in der Automatisierungs Struktur angezeigt, und die von ihm generierten scrollereignisse scheinen aus <xref:System.Windows.Controls.ItemsControl> dem-Objekt zu stammen.  
  
### <a name="override-core-methods"></a>„Kern“-Methode außer Kraft setzen  
 Der Automatisierungscode ruft Informationen über Ihr Steuerelement ab, indem er die öffentlichen Methoden der Peer-Klasse aufruft. Um Informationen über Ihr Steuerelement bereitzustellen, setzen Sie jede Methode außer Kraft, deren Name mit „Core“ endet, falls die Implementierung Ihrer Steuerelemente sich von der Implementierung unterscheidet, die von der Basis-Automatisierungspeerklasse bereitgestellt wird. Das-Steuerelement muss mindestens die-Methode <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> die-Methode implementieren, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Ihre Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> beschreibt das Steuerelement, indem <xref:System.Windows.Automation.ControlType> ein-Wert zurückgegeben wird. Obwohl Sie zurückgeben <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>können, sollten Sie einen der spezifischeren Steuerelement Typen zurückgeben, wenn er das Steuerelement genau beschreibt. Der Rückgabewert <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> erfordert zusätzliche Arbeit, damit der Anbieter implementiert [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], und [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Client Produkte können die Steuerelement Struktur, die Tastatur Interaktion und mögliche Steuerelement Muster nicht vorhersehen.  
  
 Implementieren Sie <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> -Methode und die-Methode, um anzugeben, ob das Steuerelement Dateninhalte enthält oder eine interaktive Rolle in der Benutzeroberfläche erfüllt (oder beides). Standardmäßig geben die beiden Methoden `true` zurück. Diese Einstellungen verbessern die Nutzbarkeit der Automatisierungstools, wie z.B. Sprachausgabe-Tools, die mit diesen Methoden die Automatisierungsstruktur filtern. Wenn die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode die Muster Verarbeitung an einen untergeordneten Peer überträgt, kann die-Methode des Subelements-Peers false zurückgeben, um den subelarpeer aus der Automatisierungs Struktur auszublenden. <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Beispielsweise wird der Bildlauf <xref:System.Windows.Controls.ListBox> in einem von einer <xref:System.Windows.Controls.ScrollViewer>verarbeitet, und der Automatisierungspeer für <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> wird <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> von der- <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> Methode der-Instanz zurück <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>gegeben, die dem zugeordnet ist. Daher <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> gibt die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> -Methode von zurück `false`, sodass der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> nicht in der Automatisierungs Struktur angezeigt wird.  
  
 Ihr Automatisierungspeer sollte dem Steuerelement entsprechende Standardwerte bereitstellen. Beachten Sie, dass XAML, das auf das Steuerelement verweist, ihre Peer Implementierungen von <xref:System.Windows.Automation.AutomationProperties> Kern Methoden durch Einschließen von Attributen überschreiben kann. Der folgende XAML-Code erstellt z.B. eine Schaltfläche mit zwei benutzerdefinierten [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Eigenschaften.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementieren von Musteranbietern  
 Die von einem benutzerdefinierten Anbieter implementierten Schnittstellen werden explizit deklariert, wenn das Besitz <xref:System.Windows.Controls.Control>Ende Element direkt von abgeleitet wird. Der folgende Code deklariert z. b. einen Peer für <xref:System.Windows.Controls.Control> einen, der einen Bereichs Wert implementiert.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Wenn das besitzende Steuerelement von einem bestimmten Steuerelement <xref:System.Windows.Controls.Primitives.RangeBase>, z. b., abgeleitet ist, kann der Peer von einer entsprechenden abgeleiteten Peer Klasse abgeleitet werden. In diesem Fall wird der Peer von <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>abgeleitet, der eine Basis Implementierung von <xref:System.Windows.Automation.Provider.IRangeValueProvider>bereitstellt. Der folgende Code veranschaulicht die Deklaration eines solchen Peers.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Eine Beispiel Implementierung finden Sie unter oder [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) Quellcode, der implementiert und ein benutzerdefiniertes NumericUpDown-Steuerelement verwendet.  
  
### <a name="raise-events"></a>Auslösen von Ereignissen  
 Automatisierungsclients können Automatisierungsereignisse abonnieren. Benutzerdefinierte Steuerelemente müssen Änderungen zum Steuern des Zustands melden <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> , indem Sie die-Methode aufrufen. Wenn sich ein Eigenschafts Wert ändert, wird auch <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> die-Methode aufgerufen. Der folgende Code zeigt, wie Sie das Peerobjekt aus dem Steuerelementcode abrufen und eine Methode zum Auslösen eines Ereignisses aufrufen. Als Optimierung überprüft der Code, ob Listener für diesen Ereignistyp vorhanden sind. Ereignisse werden nur dann ausgelöst, wenn Listener vorhanden sind, sodass unnötiger Aufwand vermieden wird und das Steuerelement reaktionsfähig bleibt.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierung](../../ui-automation/ui-automation-overview.md)
- [Server-Side UI Automation Provider Implementation](../../ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
- [Benutzerdefiniertes NumericUpDownC#-Steuerelement () auf GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Benutzerdefiniertes NumericUpDown-Steuerelement (Visual Basic) auf GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
