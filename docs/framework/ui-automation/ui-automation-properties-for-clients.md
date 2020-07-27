---
title: Benutzeroberflächenautomatisierungs-Eigenschaften für Clients
description: Lesen Sie eine Übersicht über die Eigenschaften der Benutzeroberflächen Automatisierung, da diese für Benutzeroberflächenautomatisierungs-Client Anwendungen verfügbar gemacht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, UI Automation clients
- UI Automation, client properties
ms.assetid: 255905af-0b17-485c-93d4-8a2db2a6524b
ms.openlocfilehash: fe78d7da154d79a5f66ee6c190b199065675841f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163132"
---
# <a name="ui-automation-properties-for-clients"></a>Benutzeroberflächenautomatisierungs-Eigenschaften für Clients
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In dieser Übersicht werden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften vorgestellt, die für Benutzeroberflächenautomatisierungs-Clientanwendungen verfügbar gemacht werden.  
  
 Eigenschaften von <xref:System.Windows.Automation.AutomationElement> -Objekten enthalten Informationen über [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Elemente, in der Regel Steuerelemente. Die Eigenschaften eines <xref:System.Windows.Automation.AutomationElement> sind generisch, das heißt, nicht spezifisch für einen Steuerelementtyp. Viele dieser Eigenschaften werden in der <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation> -Struktur verfügbar gemacht.  
  
 Steuerelementmuster verfügen auch über Eigenschaften. Die Eigenschaften von Steuerelementmustern sind für das Muster spezifisch. <xref:System.Windows.Automation.ScrollPattern> enthält z. B. Eigenschaften, mit deren Hilfe eine Clientanwendung ermitteln kann, ob ein Fenster über vertikale oder horizontale Bildlaufleisten verfügt, und welche Ansichtsgrößen und Bildlaufpositionen aktuell verwendet werden. Steuerelementmuster machen alle Eigenschaften durch eine Struktur verfügbar, z. B. durch <xref:System.Windows.Automation.ScrollPattern.ScrollPatternInformation>.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften sind schreibgeschützt. Um Eigenschaften eines Steuerelements festzulegen, müssen Sie die Methoden des entsprechenden Steuerelementmusters verwenden. Verwenden Sie z. B. <xref:System.Windows.Automation.ScrollPattern.Scroll%2A> , um die Positionswerte eines Bildlauffensters zu ändern.  
  
 Um die Leistung zu verbessern, können Eigenschaftswerte von Steuerelementen und Steuerelementmustern zwischengespeichert werden, wenn <xref:System.Windows.Automation.AutomationElement> -Objekte abgerufen werden. Weitere Informationen finden Sie unter [Caching in Benutzeroberflächenautomatisierungs-Clients](caching-in-ui-automation-clients.md).  
  
## <a name="property-ids"></a>Eigenschaften-IDs  
 Eigenschafts Bezeichner (IDs) sind eindeutige, Konstante Werte, die in-Objekten gekapselt sind <xref:System.Windows.Automation.AutomationProperty> . Benutzeroberflächenautomatisierungs-Client Anwendungen erhalten diese IDs aus der- <xref:System.Windows.Automation.AutomationElement> Klasse oder von der entsprechenden Steuerelement Muster Klasse, z <xref:System.Windows.Automation.ScrollPattern> . b.. Benutzeroberflächenautomatisierungs-Anbieter rufen sie aus <xref:System.Windows.Automation.AutomationElementIdentifiers> oder aus einer der Klassen von Steuerelementmuster-IDs ab, z. B. aus <xref:System.Windows.Automation.ScrollPatternIdentifiers>.  
  
 Die numerische <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> einer <xref:System.Windows.Automation.AutomationProperty> wird von Anbietern zum Identifizieren von Eigenschaften verwendet, die in der <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPropertyValue%2A?displayProperty=nameWithType> -Methode abgefragt werden. Im Allgemeinen müssen Clientanwendungen die <xref:System.Windows.Automation.AutomationIdentifier.Id%2A>nicht prüfen. Der <xref:System.Windows.Automation.AutomationIdentifier.ProgrammaticName%2A> wird nur zum Debuggen und für Diagnosezwecke verwendet.  
  
## <a name="property-conditions"></a>Eigenschaftsbedingungen  
 Die Eigenschaften-IDs werden zum Erstellen <xref:System.Windows.Automation.PropertyCondition> von Objekten verwendet, die zum Suchen von Objekten verwendet werden <xref:System.Windows.Automation.AutomationElement> . Sie möchten z. B. ein <xref:System.Windows.Automation.AutomationElement> mit einem bestimmten Namen oder alle aktivierten Steuerelemente suchen. Jede <xref:System.Windows.Automation.PropertyCondition> gibt eine <xref:System.Windows.Automation.AutomationProperty> -ID und den Wert an, mit dem die Eigenschaft übereinstimmen muss.  
  
 Weitere Informationen finden Sie unter den folgenden Referenzthemen:  
  
- <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.FindAll%2A>  
  
- <xref:System.Windows.Automation.TreeWalker.Condition%2A>  
  
## <a name="retrieving-properties"></a>Abrufen von Eigenschaften  
 Einige Eigenschaften von <xref:System.Windows.Automation.AutomationElement> und alle Eigenschaften einer Steuerelementmusterklasse werden als geschachtelte Eigenschaften der `Current` -Eigenschaft oder der `Cached` -Eigenschaft des <xref:System.Windows.Automation.AutomationElement> oder des Steuerelementmusterobjekts verfügbar gemacht.  
  
 Darüber hinaus kann jedes <xref:System.Windows.Automation.AutomationElement> oder jede Steuerelementmustereigenschaft, einschließlich von Eigenschaften, die in der <xref:System.Windows.Automation.AutomationElement.Cached%2A> -Struktur oder in der <xref:System.Windows.Automation.AutomationElement.Current%2A> -Struktur nicht verfügbar sind, mit einer der folgenden Methoden abgerufen werden:  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>  
  
 Diese Methoden bieten eine etwas bessere Leistung sowie Zugriff auf sämtliche Eigenschaften.  
  
 Im folgenden Codebeispiel werden die beiden Möglichkeiten zum Abrufen einer Eigenschaft eines <xref:System.Windows.Automation.AutomationElement>veranschaulicht.  
  
 [!code-csharp[UIAClient_snip#121](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#121)]
 [!code-vb[UIAClient_snip#121](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#121)]  
  
 Um Eigenschaften von Steuerelementmustern abzurufen, die von <xref:System.Windows.Automation.AutomationElement>unterstützt werden, muss das Steuerelementmusterobjekt nicht abgerufen werden. Übergeben Sie einfach eine der Mustereigenschaften-IDs an die Methode.  
  
 Im folgenden Codebeispiel werden die beiden Möglichkeiten zum Abrufen einer Eigenschaft eines Steuerelementmusters veranschaulicht.  
  
 [!code-csharp[UIAClient_snip#122](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#122)]
 [!code-vb[UIAClient_snip#122](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#122)]  
  
 Die `Get` -Methoden geben ein <xref:System.Object>zurück. Die Anwendung muss das zurückgegebene Objekt in den richtigen Typ umwandeln, bevor der Wert verwendet wird.  
  
## <a name="default-property-values"></a>Standardeigenschaftswerte  
 Wenn ein Benutzeroberflächenautomatisierungs-Anbieter eine Eigenschaft nicht implementiert, kann das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -System einen Standardwert bereitstellen. Wenn der Anbieter für ein Steuerelement die durch <xref:System.Windows.Automation.AutomationElement.HelpTextProperty>bezeichnete Eigenschaft z. B. nicht unterstützt, gibt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eine leere Zeichenfolge zurück. Wenn der Anbieter die durch <xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>bezeichnete Eigenschaft nicht unterstützt, gibt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] entsprechend `false`zurück.  
  
 Sie können dieses Verhalten ändern, indem Sie die <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> -Methodenüberladung und die <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> -Methodenüberladung verwenden. Wenn Sie `true` als zweiten Parameter angeben, gibt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] keinen Standardwert zurück, sondern stattdessen den speziellen Wert <xref:System.Windows.Automation.AutomationElement.NotSupported>.  
  
 Mit dem folgenden Beispielcode wird versucht, eine Eigenschaft aus einem Element abzurufen. Wenn die Eigenschaft nicht unterstützt wird, wird stattdessen ein von der Anwendung definierter Wert verwendet.  
  
 [!code-csharp[UIAClient_snip#123](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#123)]
 [!code-vb[UIAClient_snip#123](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#123)]  
  
 Um zu ermitteln, welche Eigenschaften von einem Element unterstützt werden, verwenden Sie <xref:System.Windows.Automation.AutomationElement.GetSupportedProperties%2A>. Dies gibt ein Array von <xref:System.Windows.Automation.AutomationProperty> -IDs zurück.  
  
## <a name="property-changed-events"></a>Durch geänderte Eigenschaften ausgelöste Ereignisse  
 Wenn sich ein Eigenschaftswert eines <xref:System.Windows.Automation.AutomationElement> oder Steuerelementmusters ändert, wird ein Ereignis ausgelöst. Eine Anwendung kann solche Ereignisse abonnieren, indem <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>aufgerufen wird, worin als letzter Parameter ein Array von <xref:System.Windows.Automation.AutomationProperty> -IDs bereitgestellt wird, mit dem die betreffenden Eigenschaften angegeben werden.  
  
 Im <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>können Sie die geänderte Eigenschaft ermitteln, indem Sie das <xref:System.Windows.Automation.AutomationPropertyChangedEventArgs.Property%2A> -Element der Ereignisargumente überprüfen. Die Argumente enthalten auch die alten und neuen Werte der geänderten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft. Diese Werte sind vom Typ <xref:System.Object> und müssen in den richtigen Typ umgewandelt werden, bevor sie verwendet werden.  
  
## <a name="additional-automationelement-properties"></a>Zusätzliche AutomationElement-Eigenschaften  
 Neben der <xref:System.Windows.Automation.AutomationElement.Current%2A> -Eigenschaftenstruktur und der <xref:System.Windows.Automation.AutomationElement.Cached%2A> -Eigenschaftenstruktur besitzt <xref:System.Windows.Automation.AutomationElement> die folgenden Eigenschaften, die über einfache Eigenschaftenaccessoren abgerufen werden.  
  
|Eigenschaft|BESCHREIBUNG|  
|--------------|-----------------|  
|<xref:System.Windows.Automation.AutomationElement.CachedChildren%2A>|Eine Auflistung von untergeordneten <xref:System.Windows.Automation.AutomationElement> -Objekten im Cache.|  
|<xref:System.Windows.Automation.AutomationElement.CachedParent%2A>|Ein übergeordnetes <xref:System.Windows.Automation.AutomationElement> -Objekt im Cache.|  
|<xref:System.Windows.Automation.AutomationElement.FocusedElement%2A>|(Statische Eigenschaft) Das <xref:System.Windows.Automation.AutomationElement> , das den Eingabefokus besitzt.|  
|<xref:System.Windows.Automation.AutomationElement.RootElement%2A>|(Statische Eigenschaft) Das Stamm- <xref:System.Windows.Automation.AutomationElement>.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](caching-in-ui-automation-clients.md)
- [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](server-side-ui-automation-provider-implementation.md)
- [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](subscribe-to-ui-automation-events.md)
