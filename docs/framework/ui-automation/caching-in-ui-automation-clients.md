---
title: Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients
description: Hier finden Sie Details zum Caching in Benutzeroberflächenautomatisierungs-Clients in .net. Caching ist als das vorab abrufen von Daten definiert.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation caching in clients
- caching, UI Automation clients
ms.assetid: 94c15031-4975-43cc-bcd5-c9439ed21c9c
ms.openlocfilehash: 029e292e60cd7c66d55b9567385bdd0e53fdebd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283522"
---
# <a name="caching-in-ui-automation-clients"></a>Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird das Zwischenspeichern von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] s-Eigenschaften und -Steuerelementmustern erläutert.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]bedeutet Zwischenspeichern, dass Daten vorab abgerufen werden. Auf die Daten kann dann ohne weitere prozessübergreifende Kommunikation zugegriffen werden. Zwischenspeichern wird normalerweise von Benutzeroberflächenautomatisierungs-Client-Anwendungen verwendet, um Eigenschaften und Steuerelementmuster in großen Mengen abzurufen. Informationen werden dann nach Bedarf aus dem Cache abgerufen. Der Cache wird von der Anwendung regelmäßig aktualisiert, üblicherweise als Reaktion auf Ereignisse, die signalisieren, dass in der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] irgendeine Änderung vorgenommen wurde.  
  
 Die Vorteile der Zwischenspeicherung sind besonders mit Windows Presentation Foundation (WPF)-Steuerelementen und benutzerdefinierten Steuerelementen mit serverseitigen Benutzeroberflächenautomatisierungs-Anbietern erkennbar. Der Zugriff auf Client seitige Anbieter, wie z. b. die Standardanbieter für Win32-Steuerelemente, ist weniger vorteilhaft.  
  
 Zwischenspeichern findet statt, wenn die Anwendung ein <xref:System.Windows.Automation.CacheRequest> aktiviert und anschließend eine beliebige Methode oder Eigenschaft verwendet, die ein <xref:System.Windows.Automation.AutomationElement>zurückgibt, zum Beispiel <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>oder <xref:System.Windows.Automation.AutomationElement.FindAll%2A>. Eine Ausnahme sind die Methoden der <xref:System.Windows.Automation.TreeWalker> -Klasse. Bei ihnen findet Zwischenspeichern nur statt, wenn als Parameter ein <xref:System.Windows.Automation.CacheRequest> angegeben ist (zum Beispiel <xref:System.Windows.Automation.TreeWalker.GetFirstChild%28System.Windows.Automation.AutomationElement%2CSystem.Windows.Automation.CacheRequest%29?displayProperty=nameWithType>).  
  
 Zwischenspeichern erfolgt auch, wenn Sie ein Ereignis abonnieren, während ein <xref:System.Windows.Automation.CacheRequest> aktiv ist. Das als Quelle eines Ereignisses an Ihren Ereignishandler übergebene <xref:System.Windows.Automation.AutomationElement> enthält die zwischengespeicherten Eigenschaften und Muster, die vom ursprünglichen <xref:System.Windows.Automation.CacheRequest>angegebenen wurden. Jegliche Änderungen, die an dem <xref:System.Windows.Automation.CacheRequest> vorgenommen werden, nachdem Sie das Ereignis abonniert haben, haben keinen Einfluss.  
  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften und -Steuerelementmuster eines Elements können zwischengespeichert werden.  
  
<a name="Options_for_Caching"></a>

## <a name="options-for-caching"></a>Optionen für ein Zwischenspeichern  

 <xref:System.Windows.Automation.CacheRequest> gibt die folgenden Optionen für ein Zwischenspeichern an.  
  
<a name="Properties_to_Cache"></a>

### <a name="properties-to-cache"></a>Eigenschaften, die zwischengespeichert werden sollen  

 Sie können zwischenzuspeichernde Eigenschaften angeben, indem Sie vor dem Aktivieren der Anforderung <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationProperty%29> für jede Eigenschaft aufrufen.  
  
<a name="Control_Patterns_to_Cache"></a>

### <a name="control-patterns-to-cache"></a>Steuerelementmuster, die zwischengespeichert werden sollen  

 Sie können zwischenzuspeichernde Steuerelementmuster angeben, indem Sie vor dem Aktivieren der Anforderung <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationPattern%29> für jedes Steuerelementmuster aufrufen. Wenn ein Muster zwischengespeichert wird, werden dessen Eigenschaften nicht automatisch zwischengespeichert. Sie müssen die Eigenschaften, die zwischengespeichert werden sollen, mit <xref:System.Windows.Automation.CacheRequest.Add%2A?displayProperty=nameWithType>angeben.  
  
<a name="Scope_of_the_Caching"></a>

### <a name="scope-and-filtering-of-caching"></a>Umfang und Filtern eines Zwischenspeicherns  

 Sie können die Elemente angeben, deren Eigenschaften und Muster Sie zwischenspeichern möchten, indem Sie vor dem Aktivieren der Anforderung die <xref:System.Windows.Automation.CacheRequest.TreeScope%2A?displayProperty=nameWithType> -Eigenschaft festlegen. Der Umfang ist relativ zu den Elementen, die abgerufen werden, während die Anforderung aktiv ist. Wenn Sie beispielsweise nur <xref:System.Windows.Automation.TreeScope.Children>festlegen und dann ein <xref:System.Windows.Automation.AutomationElement>abrufen, werden die Eigenschaften und Muster der untergeordneten Elemente dieses Elements zwischengespeichert, nicht jedoch die des Elements selbst. Um sicherzustellen, dass Zwischenspeichern für das abgerufene Element selbst ausgeführt wird, müssen Sie <xref:System.Windows.Automation.TreeScope.Element> in der <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> -Eigenschaft einschließen. Es ist nicht möglich, den Bereich auf <xref:System.Windows.Automation.TreeScope.Parent> oder <xref:System.Windows.Automation.TreeScope.Ancestors>festzulegen. Ein übergeordnetes Element kann jedoch zwischengespeichert werden, wenn ein untergeordnetes Element zwischengespeichert wird. Weitere Informationen hierzu finden Sie in diesem Thema unter „Abrufen von zwischengespeicherten untergeordneten und übergeordneten Elementen“.  
  
 Der Umfang eines Zwischenspeicherns wird auch von der <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A?displayProperty=nameWithType> -Eigenschaft beeinflusst. Standardmäßig werden nur Elemente zwischengespeichert, die in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur angezeigt werden. Sie können diese Eigenschaft jedoch ändern, sodass alle Elemente oder nur in der Inhaltsansicht angezeigte Elemente zwischengespeichert werden.  
  
<a name="Strength_of_the_Element_References"></a>

### <a name="strength-of-the-element-references"></a>Stärke der Elementverweise  

 Wenn Sie ein <xref:System.Windows.Automation.AutomationElement>abrufen, können Sie standardmäßig auf alle Eigenschaften und Muster dieses Elements, einschließlich der nicht zwischengespeicherten, zugreifen. Sie können jedoch, um die Effizienz zu erhöhen, angeben, dass sich der Verweis auf das Element nur auf zwischengespeicherte Daten bezieht, indem Sie die <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> -Eigenschaft von <xref:System.Windows.Automation.CacheRequest> auf <xref:System.Windows.Automation.AutomationElementMode.None>festlegen. In diesem Fall haben Sie keinen Zugriff auf nicht zwischengespeicherte Eigenschaften und Muster von abgerufenen Elementen. Dies bedeutet, dass Sie auf keine der Eigenschaften über <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> oder die `Current` -Eigenschaft von <xref:System.Windows.Automation.AutomationElement> oder irgendein Steuerelementmuster zugreifen können, und Sie können auch kein Muster abrufen, indem Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>verwenden. Für zwischengespeicherte Muster können Sie Methoden aufrufen, die Arrayeigenschaften wie beispielsweise <xref:System.Windows.Automation.SelectionPattern.SelectionPatternInformation.GetSelection%2A?displayProperty=nameWithType>abrufen, jedoch keine Methoden aufrufen, die Aktionen für das Steuerelement ausführen, wie etwa <xref:System.Windows.Automation.InvokePattern.Invoke%2A?displayProperty=nameWithType>.  
  
 Ein Beispiel für eine Anwendung, für die möglicherweise keine vollständigen Verweise auf Objekte erforderlich sind, ist eine Bildschirmsprachausgabe, die die Eigenschaften <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> und <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> von Elementen in einem Fenster vorab abruft, die <xref:System.Windows.Automation.AutomationElement> -Objekte selbst jedoch nicht benötigt.  
  
<a name="Activating_the_CacheRequest"></a>

## <a name="activating-the-cacherequest"></a>Aktivieren von CacheRequest  

 Ein Zwischenspeichern wird nur ausgeführt, wenn <xref:System.Windows.Automation.AutomationElement> -Objekte abgerufen werden, während für den aktuellen Thread ein <xref:System.Windows.Automation.CacheRequest> aktiv ist. Es gibt zwei Möglichkeiten, ein <xref:System.Windows.Automation.CacheRequest>-Objekt zu aktivieren.  
  
 Die übliche Methode besteht darin, <xref:System.Windows.Automation.CacheRequest.Activate%2A>aufzurufen. Diese Methode gibt ein Objekt zurück, das <xref:System.IDisposable>implementiert. Die Anforderung bleibt aktiv, solange das <xref:System.IDisposable> -Objekt vorhanden ist. Die einfachste Möglichkeit, die Lebensdauer des Objekts zu steuern, besteht darin, den-Ausdruck in einem- `using` Block (c#) oder `Using` (Visual Basic) zu schließen. Dadurch wird sichergestellt, dass die Anforderung selbst dann aus dem Stapel entfernt wird, wenn eine Ausnahme ausgelöst wird.  
  
 Eine weitere Möglichkeit, die nützlich ist, wenn Sie Cacheanforderungen schachteln möchten, besteht darin, <xref:System.Windows.Automation.CacheRequest.Push%2A>aufzurufen. Dadurch wird die Anforderung auf einem Stapel abgelegt und aktiviert. Die Anforderung bleibt aktiv, bis sie mit <xref:System.Windows.Automation.CacheRequest.Pop%2A>aus dem Stapel entfernt wird. Die Anforderung wird vorübergehend inaktiv, wenn eine andere Anforderung auf dem Stapel abgelegt wurde. Nur die oberste Anforderung auf dem Stapel ist aktiv.  
  
<a name="Retrieving_Cached_Properties"></a>

## <a name="retrieving-cached-properties"></a>Abrufen von zwischengespeicherten Eigenschaften  

 Sie können die zwischengespeicherten Eigenschaften eines Elements über die folgenden Methoden und Eigenschaften abrufen.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.Cached%2A>  
  
 Wenn sich die angeforderte Eigenschaft nicht im Cache befindet, wird eine Ausnahme ausgelöst.  
  
 <xref:System.Windows.Automation.AutomationElement.Cached%2A>macht, ähnlich wie <xref:System.Windows.Automation.AutomationElement.Current%2A>, einzelne Eigenschaften als Member einer Struktur verfügbar. Sie müssen diese Struktur jedoch nicht abrufen, denn Sie können direkt auf die einzelnen Eigenschaften zugreifen. Beispielsweise kann die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> -Eigenschaft aus `element.Cached.Name`abgerufen werden, wobei `element` ein <xref:System.Windows.Automation.AutomationElement>ist.  
  
<a name="Retrieving_Cached_Control_Patterns"></a>

## <a name="retrieving-cached-control-patterns"></a>Abrufen von zwischengespeicherten Steuerelementmustern  

 Sie können die zwischengespeicherten Steuerelementmuster eines Elements über die folgenden Methoden abrufen.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A>  
  
 Wenn sich das Muster nicht im Cache befindet, löst <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> eine Ausnahme aus, und <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> gibt `false`zurück.  
  
 Sie können die zwischengespeicherten Eigenschaften eines Steuerelementmusters über die `Cached` -Eigenschaft des Musterobjekts abrufen. Außerdem können Sie über die `Current` -Eigenschaft die aktuellen Werte abrufen, dies jedoch nur, wenn beim Abrufen von <xref:System.Windows.Automation.AutomationElementMode.None> die Option <xref:System.Windows.Automation.AutomationElement> angegeben wurde. (Der Standardwert ist<xref:System.Windows.Automation.AutomationElementMode.Full> , und bei diesem Wert ist Zugriff auf die aktuellen Werte möglich.)  
  
<a name="Retrieving_Cached_Children_and_Parents"></a>

## <a name="retrieving-cached-children-and-parents"></a>Abrufen von zwischengespeicherten untergeordneten und übergeordneten Elementen  

 Wenn Sie ein <xref:System.Windows.Automation.AutomationElement> abrufen und über die <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> -Eigenschaft der Anforderung das Zwischenspeichern der untergeordneten Elemente dieses Elements anfordern, können Sie anschließend über die <xref:System.Windows.Automation.AutomationElement.CachedChildren%2A> -Eigenschaft des von Ihnen abgerufenen Elements auf die untergeordneten Elemente zuzugreifen.  
  
 Wurde <xref:System.Windows.Automation.TreeScope.Element> in den Bereich der Cacheanforderung eingeschlossen, ist das Stammelement der Anforderung anschließend über die <xref:System.Windows.Automation.AutomationElement.CachedParent%2A> -Eigenschaft jedes untergeordneten Elements verfügbar.  
  
> [!NOTE]
> Sie können keine übergeordneten Elemente des Stammelements der Anforderung zwischenspeichern.  
  
<a name="Updating_the_Cache"></a>

## <a name="updating-the-cache"></a>Aktualisieren des Caches  

 Der Cache ist nur gültig, solange sich in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]nichts ändert. Ihre Anwendung ist dafür verantwortlich, den Cache zu aktualisieren (normalerweise als Reaktion auf Ereignisse).  
  
 Wenn Sie ein Ereignis abonnieren, während ein <xref:System.Windows.Automation.CacheRequest> aktiv ist, erhalten Sie bei jedem Aufruf Ihres Ereignishandlerdelegaten ein <xref:System.Windows.Automation.AutomationElement> mit einem aktualisierten Cache als Quelle des Ereignisses. Sie können zwischengespeicherte Informationen für ein Element auch aktualisieren, indem Sie <xref:System.Windows.Automation.AutomationElement.GetUpdatedCache%2A>aufrufen. Sie können das ursprüngliche <xref:System.Windows.Automation.CacheRequest> -Objekt übergeben, um alle Informationen zu aktualisieren, die vorher zwischengespeichert wurden.  
  
 Durch das Aktualisieren des Caches werden die Eigenschaften der vorhandenen <xref:System.Windows.Automation.AutomationElement> -Verweise nicht geändert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzeroberflächenautomatisierungs-Ereignisse für Clients](ui-automation-events-for-clients.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
- [FetchTimer-Beispiel](/previous-versions/dotnet/netframework-3.5/ms771456(v=vs.90))
