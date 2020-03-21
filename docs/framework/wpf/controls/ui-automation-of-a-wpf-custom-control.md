---
title: UI-Automatisierung eines benutzerdefinierten Steuerelements
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
ms.openlocfilehash: 9c33d0e5da70820041ba2a2881082d9f7d179fc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187508"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] stellt eine einzelne allgemeine Schnittstelle bereit, die Automatisierungsclients zum Untersuchen oder Ausführen der Benutzerschnittstellen in unterschiedlichen Plattformen und Frameworks verwenden können. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es jeweils Qualitätssicherungcode (Testcode) und Barrierefreiheitsanwendungen, z.B. die Sprachausgabe, Benutzerschnittstellenelemente zu untersuchen und Benutzerzugriff mit ihnen aus anderem Code zu simulieren. Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] für alle Plattformen finden Sie unter „Barrierefreiheit“.  
  
 In diesem Thema wird beschrieben, wie ein serverseitiger Benutzeroberflächenautomatisierungs-Anbieter, der in einer WPF-Anwendung ausgeführt wird, für ein benutzerdefiniertes Steuerelement implementiert wird. WPF unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peer-Automatisierungsobjekten, die zur Struktur der Elemente der Benutzeroberfläche parallel ist. Testcode und -anwendungen, die Barrierefreiheitsfunktionen bereitstellen, können Automatisierungspeerobjekte direkt (für Code, der gerade ausgeführt wird) oder über eine allgemeine Schnittstelle verwenden, die von [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] bereitgestellt wird.  

<a name="AutomationPeerClasses"></a>
## <a name="automation-peer-classes"></a>Automatisierungspeerklassen  
 WPF steuert [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] die Unterstützung durch eine Struktur <xref:System.Windows.Automation.Peers.AutomationPeer>von Peerklassen, die von ableiten. Gemäß der Konvention beginnen Namen von Peerklassen mit dem Klassennamen des Steuerelements und enden mit „AutomationPeer“. Beispielsweise <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> ist die Peerklasse <xref:System.Windows.Controls.Button> für die Steuerelementklasse. Die Peerklassen entsprechen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] in etwa Denkontrolltypen, sind jedoch spezifisch für WPF-Elemente. Automatisierungscode der auf WPF-Anwendungen über die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Schnittstelle zugreift, verwendet keine Automatisierungspeers direkt, jedoch kann der Automatisierungscode im selben Prozessbereich Automatisierungspeers direkt verwenden.  
  
<a name="BuiltInAutomationPeerClasses"></a>
## <a name="built-in-automation-peer-classes"></a>Integrierte Automatisierungspeerklassen  
 Elemente implementieren eine Automatisierungspeerklasse, wenn sie Schnittstellenaktivität vom Benutzer akzeptieren oder Informationen enthalten, die von Benutzern von Anwendungen der Sprachausgabe benötigt werden. Nicht alle visuellen WPF-Elemente verfügen über Automatisierungspeers. Beispiele für Klassen, die <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.TextBox>Automatisierungspeers implementieren, sind , und <xref:System.Windows.Controls.Label>. Beispiele für Klassen, die keine Automatisierungspeers <xref:System.Windows.Controls.Decorator>implementieren, <xref:System.Windows.Controls.Border>sind Klassen, <xref:System.Windows.Controls.Panel>die von <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Canvas>ableiten, z. B. , und Klassen, die auf basieren, z. B. und .  
  
 Die <xref:System.Windows.Controls.Control> Basisklasse verfügt nicht über eine entsprechende Peerklasse. Wenn Sie eine Peerklasse benötigen, um einem benutzerdefinierten Steuerelement zu entsprechen, das von <xref:System.Windows.Controls.Control>abstammt, sollten Sie die benutzerdefinierte Peerklasse von <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>ableiten.  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations-for-derived-peers"></a>Sicherheitsüberlegungen zu abgeleiteten Peers  
 Automatisierungspeers müssen in einer Teilausführungsumgebung ausgeführt werden. Code in der UIAutomationClient-Assembly ist nicht konfiguriert, in einer teilweise vertrauenswürdigen Umgebung ausgeführt zu werden, und Automatisierungspeercode sollte nicht auf diese Assembly verweisen. Stattdessen sollten Sie diese Klassen in der UIAutomationTypes-Assembly verwenden. Sie sollten z. <xref:System.Windows.Automation.AutomationElementIdentifiers> B. die Klasse aus der UIAutomationTypes-Assembly verwenden, die der <xref:System.Windows.Automation.AutomationElement> Klasse in der UIAutomationClient-Assembly entspricht. Es ist sicher, auf die UIAutomationTypes-Assembly in Automatisierungspeercode zu verweisen.  
  
<a name="PeerNavigation"></a>
## <a name="peer-navigation"></a>Peernavigation  
 Nach dem Suchen eines Automatisierungspeers <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> kann prozessinierter Code durch <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> Aufrufen der Objekte und Methoden in der Peerstruktur navigieren. Die Navigation zwischen WPF-Elementen innerhalb eines Steuerelements <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> wird durch die Implementierung der Methode durch den Peer unterstützt. Das Benutzeroberflächenautomatisierungssystem ruft diese Methode auf, um eine Struktur von Unterelementen zu erstellen, die in einem Steuerelement vorhanden sind, z.B. Listenelemente in einem Listenfeld. Die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> Standardmethode durchläuft die visuelle Struktur von Elementen, um die Struktur von Automatisierungspeers zu erstellen. Benutzerdefinierte Steuerelemente überschreiben diese Methode, um untergeordnete Elemente für Automatisierungsclients verfügbar zu machen, dabei werden die Automatisierungspeers von Elementen zurückgegeben, die Informationen ausdrücken oder Benutzerinteraktion erlauben.  
  
<a name="Customizations"></a>
## <a name="customizations-in-a-derived-peer"></a>Anpassungen in einem abgeleiteten Peer  
 Alle Klassen, die <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> von der geschützten virtuellen Methode <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>ableiten und diese enthalten. WPF <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> ruft auf, um das Automatisierungspeerobjekt für jedes Steuerelement abzubekommen. Automatisierungscode kann Peers zum Abrufen von Informationen über Merkmale und Funktionen des Steuerelements verwenden und um interaktive Verwendung zu simulieren. Ein benutzerdefiniertes Steuerelement, <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> das die Automatisierung unterstützt, muss eine <xref:System.Windows.Automation.Peers.AutomationPeer>Instanz einer Klasse überschreiben und zurückgeben, die von abstammt. Wenn z. B. ein benutzerdefiniertes Steuerelement von <xref:System.Windows.Controls.Primitives.ButtonBase> der <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Klasse abstammt, sollte das von zurückgegebene Objekt von <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>ableiten.  
  
 Wenn Sie ein benutzerdefiniertes Steuerelement implementieren, müssen Sie die „Kernmethoden“ der grundlegenden Automatisierungspeerklasse außer Kraft setzen, die das Verhalten eindeutig beschreiben und für Ihr benutzerdefiniertes Steuerelement spezifisch sind.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer außer Kraft setzen  
 Überschreiben <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Sie die Methode für Ihr benutzerdefiniertes Steuerelement, sodass es <xref:System.Windows.Automation.Peers.AutomationPeer>Ihr Anbieterobjekt zurückgibt, das direkt oder indirekt von ableiten muss.  
  
### <a name="override-getpattern"></a>GetPattern außer Kraft setzen  
 Automatisierungspeers vereinfachen zwar manche technischen Aspekte der Implementierung von serverseitigen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Anbietern, aber Automatisierungspeers von benutzerdefinierten Steuerelementen müssen dennoch Musterschnittstellen behandeln. Wie Nicht-WPF-Anbieter unterstützen Peers Steuerelementmuster, indem sie <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> Implementierungen von <xref:System.Windows.Automation.Provider.IInvokeProvider>Schnittstellen im Namespace bereitstellen, z. B. . Die Schnittstellen der Steuerelementmuster können entweder vom Peer selbst, oder von einem anderen Objekt implementiert werden. Die Implementierung des <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Peers gibt das Objekt zurück, das das angegebene Muster unterstützt. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]code ruft <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> die Methode <xref:System.Windows.Automation.Peers.PatternInterface> auf und gibt einen Enumerationswert an. Ihre Außerkraftsetzung von <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> sollte das Objekt zurückgeben, das das angegebene Muster implementiert. Wenn das Steuerelement nicht über eine benutzerdefinierte Implementierung eines Musters verfügt, können Sie die Implementierung des Basistyps <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> aufrufen, um entweder seine Implementierung oder NULL abzurufen, wenn das Muster für diesen Steuerelementtyp nicht unterstützt wird. Beispielsweise kann ein benutzerdefiniertes NumericUpDown-Steuerelement auf einen Wert [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] innerhalb eines <xref:System.Windows.Automation.Provider.IRangeValueProvider> Bereichs festgelegt werden, sodass sein Peer die Schnittstelle implementiert. Das folgende Beispiel zeigt, <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> wie die Methode des <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> Peers überschrieben wird, um auf einen Wert zu reagieren.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Eine <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode kann auch ein Unterelement als Musteranbieter angeben. Der folgende Code <xref:System.Windows.Controls.ItemsControl> zeigt, wie die Bildlaufmusterbehandlung an den Peer der internen <xref:System.Windows.Controls.ScrollViewer> Kontrolle übertragen wird.  
  
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
  
 Um ein Unterelement für die Musterbehandlung anzugeben, ruft dieser Code <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> das Unterelementobjekt ab, erstellt mithilfe der Methode einen Peer, legt die <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> Eigenschaft des neuen Peers auf den aktuellen Peer fest und gibt den neuen Peer zurück. Durch <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> Festlegen eines Unterelements wird verhindert, dass das Unterelement in der Automatisierungspeerstruktur angezeigt wird, und es werden alle Ereignisse, die vom Unterelement ausgelöst werden, als aus dem in <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>angegebenen Steuerelement stammen. Das <xref:System.Windows.Controls.ScrollViewer> Steuerelement wird nicht in der Automatisierungsstruktur angezeigt, und die <xref:System.Windows.Controls.ItemsControl> generierten Bildlaufereignisse scheinen vom Objekt zu stammen.  
  
### <a name="override-core-methods"></a>„Kern“-Methode außer Kraft setzen  
 Der Automatisierungscode ruft Informationen über Ihr Steuerelement ab, indem er die öffentlichen Methoden der Peer-Klasse aufruft. Um Informationen über Ihr Steuerelement bereitzustellen, setzen Sie jede Methode außer Kraft, deren Name mit „Core“ endet, falls die Implementierung Ihrer Steuerelemente sich von der Implementierung unterscheidet, die von der Basis-Automatisierungspeerklasse bereitgestellt wird. Mindestens muss Das Steuerelement die <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> und die Methoden implementieren, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Ihre Implementierung <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> von beschreibt Ihr <xref:System.Windows.Automation.ControlType> Steuerelement, indem Sie einen Wert zurückgeben. Obwohl Sie <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>zurückkehren können, sollten Sie einen der spezifischeren Steuerelementtypen zurückgeben, wenn er das Steuerelement genau beschreibt. Ein Rückgabewert <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> von erfordert zusätzliche Arbeit [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]für [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] den Anbieter, um zu implementieren, und Clientprodukte sind nicht in der Lage, die Steuerungsstruktur, die Tastaturinteraktion und mögliche Steuerelementmuster vorherzusehen.  
  
 Implementieren <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> Sie <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> die und Methoden, um anzugeben, ob das Steuerelement Dateninhalte enthält oder eine interaktive Rolle in der Benutzeroberfläche (oder beides) erfüllt. Standardmäßig geben die beiden Methoden `true` zurück. Diese Einstellungen verbessern die Nutzbarkeit der Automatisierungstools, wie z.B. Sprachausgabe-Tools, die mit diesen Methoden die Automatisierungsstruktur filtern. Wenn <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Ihre Methode die Musterbehandlung an einen Subelementpeer <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> überträgt, kann die Methode des Subelementpeers false zurückgeben, um den Subelementpeer aus der Automatisierungsstruktur auszublenden. <xref:System.Windows.Controls.ListBox> Beispielsweise wird das Scrollen in a <xref:System.Windows.Controls.ScrollViewer>von einem behandelt, und der Automatisierungspeer <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> für wird von der <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Methode zurückgegeben, die <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> dem <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>zugeordnet ist. Daher wird <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> die <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> Methode `false`der Rückgabe <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> zurückgegeben, sodass die nicht in der Automatisierungsstruktur angezeigt wird.  
  
 Ihr Automatisierungspeer sollte dem Steuerelement entsprechende Standardwerte bereitstellen. Beachten Sie, dass XAML, das auf Ihr Steuerelement verweist, Ihre Peerimplementierungen von Kernmethoden überschreiben kann, indem Attribute einschließen. <xref:System.Windows.Automation.AutomationProperties> Der folgende XAML-Code erstellt z.B.. eine Schaltfläche mit zwei benutzerdefinierten [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]-Eigenschaften.  
  
```xaml  
<Button AutomationProperties.Name="Special"
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementieren von Musteranbietern  
 Die von einem benutzerdefinierten Anbieter implementierten Schnittstellen werden explizit deklariert, wenn das besitzende Element direkt von <xref:System.Windows.Controls.Control>abgeleitet wird. Der folgende Code deklariert z. <xref:System.Windows.Controls.Control> B. einen Peer für einen, der einen Bereichswert implementiert.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Wenn das besitzende Steuerelement von einem bestimmten Steuerelementtyp abgeleitet wird, z. <xref:System.Windows.Controls.Primitives.RangeBase>B. , kann der Peer von einer entsprechenden abgeleiteten Peerklasse abgeleitet werden. In diesem Fall würde der <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>Peer von ableiten, <xref:System.Windows.Automation.Provider.IRangeValueProvider>der eine Basisimplementierung von bereitstellt. Der folgende Code veranschaulicht die Deklaration eines solchen Peers.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Eine Beispielimplementierung finden Sie im Quellcode [von C-](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) oder [Visual Basic,](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) der ein benutzerdefiniertes NumericUpDown-Steuerelement implementiert und verwendet.  
  
### <a name="raise-events"></a>Auslösen von Ereignissen  
 Automatisierungsclients können Automatisierungsereignisse abonnieren. Benutzerdefinierte Steuerelemente müssen Änderungen an <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> den Kontrollstatus melden, indem die Methode aufgerufen wird. Wenn sich ein Eigenschaftswert <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> ändert, rufen Sie die Methode auf. Der folgende Code zeigt, wie Sie das Peerobjekt aus dem Steuerelementcode abrufen und eine Methode zum Auslösen eines Ereignisses aufrufen. Als Optimierung überprüft der Code, ob Listener für diesen Ereignistyp vorhanden sind. Ereignisse werden nur dann ausgelöst, wenn Listener vorhanden sind, sodass unnötiger Aufwand vermieden wird und das Steuerelement reaktionsfähig bleibt.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Benutzeroberflächenautomatisierung](../../ui-automation/ui-automation-overview.md)
- [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [NumericUpDown benutzerdefiniertes Steuerelement (C-Steuerelement) auf GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [NumericUpDown benutzerdefiniertes Steuerelement (Visual Basic) auf GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
