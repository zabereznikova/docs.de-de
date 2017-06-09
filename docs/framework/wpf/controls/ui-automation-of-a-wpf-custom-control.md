---
title: "Benutzeroberfl&#228;chenautomatisierung eines benutzerdefinierten WPF-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Benutzerdefinierte Steuerelemente [WPF], Anwenden der Benutzeroberflächenautomatisierung"
  - "Eingabehilfen [WPF], anwenden auf benutzerdefinierte Steuerelemente"
  - "Benutzerdefinierte Steuerelemente [WPF], optimieren behindertengerechter Software"
  - "Verwenden mit benutzerdefinierten Steuerelementen Benutzeroberflächenautomatisierung [WPF]"
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Benutzeroberfl&#228;chenautomatisierung eines benutzerdefinierten WPF-Steuerelements
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]Stellt einer einzelnen, allgemeinen Benutzeroberfläche, über die Automatisierungsclients Clients verwenden können, um zu überprüfen, oder die Benutzeroberflächen einer Vielzahl von Plattformen und Frameworks. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]ermöglicht es Code Quality-Versicherungsunternehmen (Test) und die Eingabehilfen wie Bildschirmsprachausgaben Benutzeroberflächenelemente untersuchen und simulieren von Benutzerinteraktion mit ihnen von anderem Code. Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] auf allen Plattformen finden Sie unter Eingabehilfen.  
  
 Dieses Thema beschreibt, wie Sie serverseitige Benutzeroberflächenautomatisierungs-Anbieter für ein benutzerdefiniertes Steuerelement zu implementieren, die in einer WPF-Anwendung ausgeführt wird. WPF unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peer-Automatisierungsobjekte, die die Struktur der Elemente der Benutzeroberfläche entspricht. Testen von Code und Anwendungen, die Eingabehilfen können Peer Automatisierungsobjekte (bei prozessinternen Code) direkt oder über die allgemeine Schnittstelle durch [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Peer-Automatisierungsklassen  
 WPF-Steuerelemente unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] über eine Struktur von Peerklassen, die von abgeleitet <xref:System.Windows.Automation.Peers.AutomationPeer>. Gemäß der Konvention Peernamen-Klasse mit dem Namen der Steuerelementklasse beginnen und enden mit "AutomationPeer". Beispielsweise <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> ist die Peerklasse für die <xref:System.Windows.Controls.Button> Klasse steuern. Die Peerklassen entsprechen weitgehend den [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] gelten jedoch spezifisch für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Elemente. Automatisierungscode für WPF-Anwendung über Zugriff auf die [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Schnittstelle verwendet keine Automatisierungspeers direkt, aber Automatisierungscode im selben Prozessraum kann Automatisierungspeers direkt verwenden.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Integrierte Automatisierungspeerklassen  
 Elemente implementieren eine Automatisierungspeerklasse Aktivität des Benutzers akzeptiert, oder wenn sie vom Benutzer Bildschirmsprachausgabe Anwendung benötigten Informationen enthalten. Nicht alle visuellen WPF-Elemente verfügen über Automatisierungspeers. Beispiele für Klassen, die Automatisierungspeers zu implementieren sind <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, und <xref:System.Windows.Controls.Label>. Beispiele für Klassen, die keine Automatisierungspeers implementieren sind abgeleitete Klassen <xref:System.Windows.Controls.Decorator>, wie z. B. <xref:System.Windows.Controls.Border>, und Klassen, die auf der Grundlage <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Canvas>.  
  
 Die Basis <xref:System.Windows.Controls.Control> -Klasse weist keine entsprechende Peerklasse. Wenn benötigen wir eine Peerklasse, um ein benutzerdefiniertes Steuerelement zu entsprechen, die von abgeleitet <xref:System.Windows.Controls.Control>, sollten Sie die benutzerdefinierte Peerklasse von ableiten <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Sicherheitsaspekte für abgeleitete Peers  
 Automatisierungspeers müssen in einer teilweise vertrauenswürdigen Umgebung ausführen. Code in der UIAutomationClient-Assembly ist nicht so konfiguriert, dass in einer teilweise vertrauenswürdigen Umgebung ausgeführt, und Peer-Automatisierungscode sollte nicht auf diese Assembly verweisen. Sie sollten stattdessen die Klassen in der UIAutomationTypes-Assembly verwenden. Sie sollten z. B. Verwenden der <xref:System.Windows.Automation.AutomationElementIdentifiers> -Klasse in der UIAutomationTypes-Assembly, entspricht die <xref:System.Windows.Automation.AutomationElement> -Klasse in der UIAutomationClient-Assembly. Es ist sicher auf die UIAutomationTypes-Assembly in Peer-Automatisierungscode verweisen.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Peer-Navigation  
 Nach dem Suchen nach einem Automatisierungspeer in-Process-Code kann in der Peerstruktur navigieren durch Aufrufen des Objekts <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> Methoden. Navigation zwischen den [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Elemente innerhalb eines Steuerelements wird durch die Peer-Implementierung von unterstützt die <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> Methode. Die Benutzeroberflächenautomatisierungs-System ruft diese Methode, um eine Struktur von Unterelementen in einem Steuerelement enthaltenen zu erstellen. Elemente in einem Listenfeld z. B. aufzulisten. Die Standardeinstellung <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=fullName> Methode durchläuft die visuelle Struktur von Elementen, die die Struktur von Automatisierungspeers zu erstellen. Benutzerdefinierte Steuerelemente überschreiben diese Methode zum Verfügbarmachen von untergeordneten Elementen Automatisierungsclients, Zurückgeben von Elementen, die Informationen vermitteln oder Benutzerinteraktionen ermöglichen die Automatisierungspeers.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Anpassungen in einem abgeleiteten Peer  
 Alle Klassen, die von abgeleitet <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> enthalten die geschützte virtuelle Methode <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF ruft <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> , Peer-Automatisierungsobjekt für jedes Steuerelement abzurufen. Automatisierungscode können Peers zum Abrufen von Informationen über Merkmale und Funktionen des Steuerelements und interaktive Verwendung zu simulieren. Ein benutzerdefiniertes Steuerelement, das Automatisierung unterstützt muss überschreiben <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> und eine Instanz einer Klasse, die von abgeleitet zurückgeben <xref:System.Windows.Automation.Peers.AutomationPeer>. Angenommen, ein benutzerdefiniertes Steuerelement abgeleitet der <xref:System.Windows.Controls.Primitives.ButtonBase> -Klasse, und klicken Sie dann auf das zurückgegebene Objekt <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> ableiten soll <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Wenn Sie ein benutzerdefiniertes Steuerelement zu implementieren, müssen Sie die Methoden "Core" aus der Basisklasse Automation Peer-Klasse überschreiben, die Verhalten eindeutig und für das benutzerdefinierte Steuerelement beschreiben.  
  
### <a name="override-oncreateautomationpeer"></a>Überschreiben von OnCreateAutomationPeer  
 Überschreiben Sie die <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> Methode für das benutzerdefinierte Steuerelement so, dass die It das Anbieterobjekt zurück, das direkt oder indirekt von abgeleitet werden müssen <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Überschreiben von GetPattern  
 Automatisierungspeers zu vereinfachen, einige Aspekte der serverseitigen Implementierung [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Anbieter, benutzerdefiniertes Steuerelement Automatisierungspeers müssen noch behandeln Steuerelementmuster-Schnittstellen. Wie nicht-WPF-Anbieter Peers Unterstützung von Steuerelementmustern durch Bereitstellung von Schnittstellen in der <xref:System.Windows.Automation.Provider?displayProperty=fullName> -Namespace, z. B. <xref:System.Windows.Automation.Provider.IInvokeProvider>. Die Steuerelementmuster-Schnittstellen können vom Peer selbst oder von einem anderen Objekt implementiert werden. Die Peer-Implementierung von <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> gibt das Objekt, das das angegebene Muster unterstützt. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]Code wird die <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> Methode und gibt eine <xref:System.Windows.Automation.Peers.PatternInterface> -Enumerationswert. Überschreiben der <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> sollte zurückgegeben werden das Objekt, das das angegebene Muster implementiert. Wenn das Steuerelement nicht über eine benutzerdefinierte Implementierung eines Musters verfügt, können Sie Implementierung des Basistyps aufrufen <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> entweder dessen Implementierung oder Null abgerufen, wenn das Muster nicht für diesen Steuerelementtyp unterstützt wird. Beispielsweise kann ein benutzerdefiniertes NumericUpDown-Steuerelement festgelegt werden, auf einen Wert innerhalb eines Bereichs so seine [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Peer implementiert die <xref:System.Windows.Automation.Provider.IRangeValueProvider> Schnittstelle. Das folgende Beispiel zeigt wie des Peers <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> -Methode überschrieben wird, zum Antworten auf eine <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> Wert.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Ein <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> -Methode kann auch ein Unterelement als Musteranbieter angeben. Der folgende code zeigt, wie <xref:System.Windows.Controls.ItemsControl> überträgt Blättern Musterbehandlung an den Peer des internen <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
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
  
 Zum Angeben einer Unterelements für diesen Code wird das untergeordnete Objekt, erstellt einen Peer mit dem <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> -Methode legt die <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> -Eigenschaft des neuen Peers auf den aktuellen Peer, und gibt den neuen Peer zurück. Festlegen von <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> für ein Unterelement verhindert, dass das untergeordnete Element in der Peer-Struktur angezeigt werden, und kennzeichnet alle durch das Unterelement ausgelösten Ereignisse als Ursprung des Steuerelements im angegebenen <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. Die <xref:System.Windows.Controls.ScrollViewer> Steuerelement wird in der Automatisierungsstruktur nicht angezeigt und Bildlauf Ereignisse, die es generiert zu stammen scheinen die <xref:System.Windows.Controls.ItemsControl> Objekt.  
  
### <a name="override-core-methods"></a>Überschreiben Sie Methoden von "Core"  
 Automatisierungscode Ruft Informationen über das Steuerelement durch Aufrufen der öffentliche Methoden der Peerklasse. Um Informationen über das Steuerelement bereitzustellen, überschreiben Sie jede Methode, deren Name mit "Core" endet, wenn es sich bei der Implementierung der Steuerelemente von der Basis Automatisierungspeerklasse bereitgestellten unterscheidet. Mindestens ein Steuerelement implementieren muss die <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> Methoden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Die Implementierung der <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> beschreibt das Steuerelement durch die Rückgabe einer <xref:System.Windows.Automation.ControlType> Wert. Sie haben zwar zurückzugeben <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName>, sollten Sie einen spezifischeren Steuerelementtyp zurückgeben, wenn sie das Steuerelement genau beschreibt. Ein Rückgabewert von <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName> Arbeitsaufwand für den Anbieter zum Implementieren [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], und [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Clientprodukte Steuerelementstruktur, Tastaturinteraktion und mögliche Steuerelementmuster nicht im Vorfeld definieren.  
  
 Implementieren der <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> und <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methoden, um anzugeben, ob das Steuerelement Daten enthält oder zur Interaktion in der Benutzeroberfläche (oder beides dient). Standardmäßig beide Methoden zurückgeben `true`. Diese Einstellungen verbessert die Verwendbarkeit der Automation-Tools wie z. B. die Bildschirmsprachausgabe, die diese Methoden verwenden können, um die Benutzeroberflächenautomatisierungs-Struktur zu filtern. Wenn Ihre <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Methode überträgt Muster ein Unterelement, damit der Peer des Peers Ausnahmebehandlung <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode kann für Peer in der Automatisierungsstruktur ausblenden "false" zurückgeben. Z. B. Bildlauf in einer <xref:System.Windows.Controls.ListBox> erfolgt durch eine <xref:System.Windows.Controls.ScrollViewer>, und der Automatisierungspeer für <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> von zurückgegeben wird der <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> zugeordnete der <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Daher die <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> Methode der <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> gibt `false`, sodass die <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> wird in der Automatisierungsstruktur nicht angezeigt.  
  
 Die Automatisierungspeer sollten entsprechende Standardwerte für das Steuerelement bereitstellen. Beachten Sie, dass XAML, die das Steuerelement verweist auf die Peer-Implementierungen der wichtigsten Methoden, dazu überschreiben kann <xref:System.Windows.Automation.AutomationProperties> Attribute. Der folgende XAML-Code erstellt z. B. eine Schaltfläche mit zwei benutzerdefinierte [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementieren von Musteranbieter  
 Von einem benutzerdefinierten Anbieter implementierten Schnittstellen werden explizit deklariert werden, wenn das besitzende Element direkt abgeleitet <xref:System.Windows.Controls.Control>. Der folgende Code deklariert beispielsweise einen Peer für eine <xref:System.Windows.Controls.Control> , der einen Bereichswert implementiert.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Wenn eine bestimmte Art von Steuerelement wie z. B. besitzenden Steuerelements abgeleitet <xref:System.Windows.Controls.Primitives.RangeBase>, kann der Peer von einer äquivalenten abgeleiteten Peerklasse abgeleitet werden. In diesem Fall würde der Peer leiten Sie von <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, der eine grundlegende Implementierung der bereitstellt <xref:System.Windows.Automation.Provider.IRangeValueProvider>. Der folgende Code zeigt die Deklaration eines solchen Peers.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Ein Beispiel für eine Implementierung, finden Sie unter [benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung](http://go.microsoft.com/fwlink/?LinkID=160025).  
  
### <a name="raise-events"></a>Auslösen von Ereignissen  
 Automatisierungsclients können Automatisierungsereignisse abonnieren. Benutzerdefinierte Steuerelemente müssen melden Änderungen an den Steuerelementzustand durch Aufrufen der <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> Methode. Wenn sich ein Eigenschaftswert ändert, aufrufen, wird entsprechend der <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> Methode. Der folgende Code zeigt, wie Sie das Peerobjekt aus dem Steuerelementcode abrufen und Aufrufen einer Methode zum Auslösen eines Ereignisses. Zur Optimierung ermittelt der Code, wenn keine Listener für diesen Ereignistyp vorhanden sind. Auslösen des Ereignisses nur dann, wenn Listener verhindert unnötigen Aufwand und das Steuerelement reaktionsfähig bleiben.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierung](../../../../docs/framework/ui-automation/ui-automation-overview.md)   
 [Benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung](http://go.microsoft.com/fwlink/?LinkID=160025)   
 [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)