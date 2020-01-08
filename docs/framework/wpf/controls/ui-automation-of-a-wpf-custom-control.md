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
ms.openlocfilehash: 1cafb6cf8fd5096e2c17d2687ec390db06faf873
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636067"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] stellt eine einzelne allgemeine Schnittstelle bereit, die Automatisierungsclients zum Untersuchen oder Ausführen der Benutzerschnittstellen in unterschiedlichen Plattformen und Frameworks verwenden können. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es jeweils Qualitätssicherungcode (Testcode) und Barrierefreiheitsanwendungen, z.B. die Sprachausgabe, Benutzerschnittstellenelemente zu untersuchen und Benutzerzugriff mit ihnen aus anderem Code zu simulieren. Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] für alle Plattformen finden Sie unter „Barrierefreiheit“.  
  
 In diesem Thema wird beschrieben, wie ein serverseitiger Benutzeroberflächenautomatisierungs-Anbieter, der in einer WPF-Anwendung ausgeführt wird, für ein benutzerdefiniertes Steuerelement implementiert wird. WPF unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peer-Automatisierungsobjekten, die zur Struktur der Elemente der Benutzeroberfläche parallel ist. Testcode und -anwendungen, die Barrierefreiheitsfunktionen bereitstellen, können Automatisierungspeerobjekte direkt (für Code, der gerade ausgeführt wird) oder über eine allgemeine Schnittstelle verwenden, die von [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] bereitgestellt wird.  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Automatisierungspeerklassen  
 WPF-Steuerelemente unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] durch eine Struktur von Peer Klassen, die von <xref:System.Windows.Automation.Peers.AutomationPeer>abgeleitet werden. Gemäß der Konvention beginnen Namen von Peerklassen mit dem Klassennamen des Steuerelements und enden mit „AutomationPeer“. <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> ist beispielsweise die Peer Klasse für die <xref:System.Windows.Controls.Button> Steuerelement Klasse. Die Peer Klassen entsprechen in etwa [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Steuerelement Typen, sind aber spezifisch für WPF-Elemente. Automatisierungscode der auf WPF-Anwendungen über die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Schnittstelle zugreift, verwendet keine Automatisierungspeers direkt, jedoch kann der Automatisierungscode im selben Prozessbereich Automatisierungspeers direkt verwenden.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Integrierte Automatisierungspeerklassen  
 Elemente implementieren eine Automatisierungspeerklasse, wenn sie Schnittstellenaktivität vom Benutzer akzeptieren oder Informationen enthalten, die von Benutzern von Anwendungen der Sprachausgabe benötigt werden. Nicht alle visuellen WPF-Elemente verfügen über Automatisierungspeers. Beispiele für Klassen, die Automatisierungs Peers implementieren, sind <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>und <xref:System.Windows.Controls.Label>. Beispiele für Klassen, die keine Automatisierungs Peers implementieren, sind Klassen, die von <xref:System.Windows.Controls.Decorator>abgeleitet werden, z. b. <xref:System.Windows.Controls.Border>, und Klassen, die auf <xref:System.Windows.Controls.Panel>basieren, z. b. <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Canvas>.  
  
 Die Basis <xref:System.Windows.Controls.Control> Klasse verfügt nicht über eine entsprechende Peer Klasse. Wenn Sie eine Peer Klasse benötigen, die einem benutzerdefinierten Steuerelement entspricht, das von <xref:System.Windows.Controls.Control>abgeleitet ist, sollten Sie die benutzerdefinierte Peer Klasse von <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>ableiten.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Sicherheitsüberlegungen zu abgeleiteten Peers  
 Automatisierungspeers müssen in einer Teilausführungsumgebung ausgeführt werden. Code in der UIAutomationClient-Assembly ist nicht konfiguriert, in einer teilweise vertrauenswürdigen Umgebung ausgeführt zu werden, und Automatisierungspeercode sollte nicht auf diese Assembly verweisen. Stattdessen sollten Sie diese Klassen in der UIAutomationTypes-Assembly verwenden. Sie sollten z. b. die <xref:System.Windows.Automation.AutomationElementIdentifiers>-Klasse aus der UIAutomationTypes-Assembly verwenden, die der <xref:System.Windows.Automation.AutomationElement>-Klasse in der UIAutomationClient-Assembly entspricht. Es ist sicher, auf die UIAutomationTypes-Assembly in Automatisierungspeercode zu verweisen.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Peernavigation  
 Nach dem Auffinden eines Automatisierungspeer kann der Prozess interne Code durch Aufrufen der <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A>-und <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> Methoden des Objekts durch die Peer Struktur navigieren. Die Navigation zwischen WPF-Elementen in einem-Steuerelement wird von der-Implementierung des-<xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> der-Methode des Peers unterstützt. Das Benutzeroberflächenautomatisierungssystem ruft diese Methode auf, um eine Struktur von Unterelementen zu erstellen, die in einem Steuerelement vorhanden sind, z.B. Listenelemente in einem Listenfeld. Die Standard <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType>-Methode durchläuft die visuelle Struktur von Elementen, um die Struktur von Automatisierungspeers zu erstellen. Benutzerdefinierte Steuerelemente überschreiben diese Methode, um untergeordnete Elemente für Automatisierungsclients verfügbar zu machen, dabei werden die Automatisierungspeers von Elementen zurückgegeben, die Informationen ausdrücken oder Benutzerinteraktion erlauben.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Anpassungen in einem abgeleiteten Peer  
 Alle Klassen, die von <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> abgeleitet sind, enthalten die geschützte virtuelle Methode <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF ruft <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> auf, um das Automatisierungs Peer Objekt für jedes Steuerelement zu erhalten. Automatisierungscode kann Peers zum Abrufen von Informationen über Merkmale und Funktionen des Steuerelements verwenden und um interaktive Verwendung zu simulieren. Ein benutzerdefiniertes Steuerelement, das Automation unterstützt, muss <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> überschreiben und eine Instanz einer Klasse zurückgeben, die von <xref:System.Windows.Automation.Peers.AutomationPeer>abgeleitet wird Wenn ein benutzerdefiniertes Steuerelement beispielsweise von der <xref:System.Windows.Controls.Primitives.ButtonBase>-Klasse abgeleitet ist, sollte das von <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> zurückgegebene Objekt von <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>abgeleitet werden.  
  
 Wenn Sie ein benutzerdefiniertes Steuerelement implementieren, müssen Sie die „Kernmethoden“ der grundlegenden Automatisierungspeerklasse außer Kraft setzen, die das Verhalten eindeutig beschreiben und für Ihr benutzerdefiniertes Steuerelement spezifisch sind.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer außer Kraft setzen  
 Überschreiben Sie die <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>-Methode für das benutzerdefinierte Steuerelement, sodass es das Anbieter Objekt zurückgibt, das direkt oder indirekt von <xref:System.Windows.Automation.Peers.AutomationPeer>abgeleitet werden muss.  
  
### <a name="override-getpattern"></a>GetPattern außer Kraft setzen  
 Automatisierungspeers vereinfachen zwar manche technischen Aspekte der Implementierung von serverseitigen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Anbietern, aber Automatisierungspeers von benutzerdefinierten Steuerelementen müssen dennoch Musterschnittstellen behandeln. Wie nicht-WPF-Anbieter unterstützen Peers Steuerelement Muster, indem Sie Implementierungen von Schnittstellen im <xref:System.Windows.Automation.Provider?displayProperty=nameWithType>-Namespace bereitstellen, z. b. <xref:System.Windows.Automation.Provider.IInvokeProvider>. Die Schnittstellen der Steuerelementmuster können entweder vom Peer selbst, oder von einem anderen Objekt implementiert werden. Die Peer-Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> gibt das Objekt zurück, das das angegebene Muster unterstützt. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Code Ruft die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>-Methode auf und gibt einen <xref:System.Windows.Automation.Peers.PatternInterface>-Enumerationswert an. Die außer Kraft Setzung von <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> sollte das Objekt zurückgeben, das das angegebene Muster implementiert. Wenn das Steuerelement nicht über eine benutzerdefinierte Implementierung eines Musters verfügt, können Sie die Implementierung des Basistyps <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> aufrufen, um entweder seine Implementierung abzurufen, oder NULL, wenn das Muster für diesen Steuerelement Typen nicht unterstützt wird. Beispielsweise kann ein benutzerdefiniertes NumericUpDown-Steuerelement auf einen Wert innerhalb eines Bereichs festgelegt werden, sodass der [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Peer die <xref:System.Windows.Automation.Provider.IRangeValueProvider>-Schnittstelle implementiert. Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>-Methode des Peers überschrieben wird, um auf einen <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> Wert zu reagieren.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Eine <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>-Methode kann auch ein Unterelement als Muster Anbieter angeben. Der folgende Code zeigt, wie <xref:System.Windows.Controls.ItemsControl> die Verarbeitung von scrollmustern an den Peer seines internen <xref:System.Windows.Controls.ScrollViewer> Steuer Elements überträgt.  
  
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
  
 Um ein Unterelement für die Muster Behandlung anzugeben, ruft dieser Code das untergeordnete Objekt ab, erstellt mithilfe der <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A>-Methode einen Peer, legt die <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>-Eigenschaft des neuen Peers auf den aktuellen Peer fest und gibt den neuen Peer zurück. Wenn Sie <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> für ein Unterelement festlegen, wird verhindert, dass das Unterelement in der Automatisierungs Peer Struktur angezeigt wird, und es werden alle Ereignisse, die vom Unterelement ausgelöst werden, als Ausgangswert von dem in <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>angegebenen Steuerelement festgelegt. Das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement wird nicht in der Automatisierungs Struktur angezeigt, und die von ihm generierten scrollereignisse scheinen aus dem <xref:System.Windows.Controls.ItemsControl>-Objekt zu stammen.  
  
### <a name="override-core-methods"></a>„Kern“-Methode außer Kraft setzen  
 Der Automatisierungscode ruft Informationen über Ihr Steuerelement ab, indem er die öffentlichen Methoden der Peer-Klasse aufruft. Um Informationen über Ihr Steuerelement bereitzustellen, setzen Sie jede Methode außer Kraft, deren Name mit „Core“ endet, falls die Implementierung Ihrer Steuerelemente sich von der Implementierung unterscheidet, die von der Basis-Automatisierungspeerklasse bereitgestellt wird. Das Steuerelement muss mindestens die Methoden <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> implementieren, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Ihre Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> beschreibt das Steuerelement, indem ein <xref:System.Windows.Automation.ControlType> Wert zurückgegeben wird. Obwohl Sie <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>zurückgeben können, sollten Sie einen der spezifischeren Steuerelement Typen zurückgeben, wenn das Steuerelement korrekt beschrieben wird. Der Rückgabewert <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> erfordert zusätzliche Arbeit, damit der Anbieter [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]implementiert, und [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Client Produkte nicht in der Lage sind, die Steuerelement Struktur, die Tastatur Interaktion und mögliche Steuerelement Muster zu antizipieren.  
  
 Implementieren Sie die Methoden <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>, um anzugeben, ob das Steuerelement Dateninhalte enthält oder eine interaktive Rolle in der Benutzeroberfläche erfüllt (oder beides). Standardmäßig geben die beiden Methoden `true` zurück. Diese Einstellungen verbessern die Nutzbarkeit der Automatisierungstools, wie z.B. Sprachausgabe-Tools, die mit diesen Methoden die Automatisierungsstruktur filtern. Wenn die <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>-Methode die Muster Verarbeitung an einen untergeordneten Peer überträgt, kann die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>-Methode des Subelements-Peers false zurückgeben, um den subelarpeer aus der Automatisierungs Struktur auszublenden. Beispielsweise wird der Bildlauf in einer <xref:System.Windows.Controls.ListBox> von einem <xref:System.Windows.Controls.ScrollViewer>behandelt, und der Automatisierungspeer für <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> wird von der <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>-Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> zurückgegeben, die mit dem <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>verknüpft ist. Daher gibt die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>-Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> `false`zurück, sodass der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> nicht in der Automatisierungs Struktur angezeigt wird.  
  
 Ihr Automatisierungspeer sollte dem Steuerelement entsprechende Standardwerte bereitstellen. Beachten Sie, dass XAML, das auf das Steuerelement verweist, ihre Peer Implementierungen von Kern Methoden überschreiben kann, indem <xref:System.Windows.Automation.AutomationProperties> Attribute eingeschlossen werden Der folgende XAML-Code erstellt z.B. eine Schaltfläche mit zwei benutzerdefinierten [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Eigenschaften.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementieren von Musteranbietern  
 Die von einem benutzerdefinierten Anbieter implementierten Schnittstellen werden explizit deklariert, wenn das besitzende Element direkt von <xref:System.Windows.Controls.Control>abgeleitet ist. Der folgende Code deklariert z. b. einen Peer für eine <xref:System.Windows.Controls.Control>, die einen Bereichs Wert implementiert.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Wenn das besitzende Steuerelement von einer bestimmten Art von Steuerelement abgeleitet wird, z. b. <xref:System.Windows.Controls.Primitives.RangeBase>, kann der Peer von einer entsprechenden abgeleiteten Peer Klasse abgeleitet werden. In diesem Fall wird der Peer von <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>abgeleitet, der eine Basis Implementierung von <xref:System.Windows.Automation.Provider.IRangeValueProvider>bereitstellt. Der folgende Code veranschaulicht die Deklaration eines solchen Peers.  
  
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
 Automatisierungsclients können Automatisierungsereignisse abonnieren. Benutzerdefinierte Steuerelemente müssen Änderungen zum Steuern des Zustands melden, indem Sie die <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A>-Methode aufrufen. Wenn sich ein Eigenschafts Wert ändert, wird auch die <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A>-Methode aufgerufen. Der folgende Code zeigt, wie Sie das Peerobjekt aus dem Steuerelementcode abrufen und eine Methode zum Auslösen eines Ereignisses aufrufen. Als Optimierung überprüft der Code, ob Listener für diesen Ereignistyp vorhanden sind. Ereignisse werden nur dann ausgelöst, wenn Listener vorhanden sind, sodass unnötiger Aufwand vermieden wird und das Steuerelement reaktionsfähig bleibt.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierung](../../ui-automation/ui-automation-overview.md)
- [Server-Side UI Automation Provider Implementation](../../ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
- [Benutzerdefiniertes NumericUpDownC#-Steuerelement () auf GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Benutzerdefiniertes NumericUpDown-Steuerelement (Visual Basic) auf GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
