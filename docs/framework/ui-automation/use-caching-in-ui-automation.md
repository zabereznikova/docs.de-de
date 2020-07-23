---
title: Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung
description: Weitere Informationen finden Sie unter Verwenden von Caching in der Benutzeroberflächen Automatisierung. Lesen Sie die Schritte zum Aktivieren einer Cache Anforderung, zum Zwischenspeichern von AutomationElement-Eigenschaften und zum erhalten von zwischengespeicherten Mustern.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: 8dff9db77e39dc66a16b6a7b395c76a3c768d48e
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924486"
---
# <a name="use-caching-in-ui-automation"></a>Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Abschnitt wird gezeigt, wie ein Zwischenspeichern von <xref:System.Windows.Automation.AutomationElement> -Eigenschaften und Steuerelementmustern implementiert wird.  
  
### <a name="activate-a-cache-request"></a>Aktivieren einer Cacheanforderung  
  
1. Erstellen Sie eine <xref:System.Windows.Automation.CacheRequest>.  
  
2. Geben Sie über <xref:System.Windows.Automation.CacheRequest.Add%2A>die Eigenschaften und Muster an, die zwischengespeichert werden sollen.  
  
3. Geben Sie den Umfang des Zwischenspeicherns an, indem Sie die <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> -Eigenschaft festlegen.  
  
4. Geben Sie die Ansicht der Unterstruktur an, indem Sie die <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> -Eigenschaft festlegen.  
  
5. Legen Sie die <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> -Eigenschaft auf <xref:System.Windows.Automation.AutomationElementMode.None> fest, wenn Sie die Effizienz dadurch steigern möchten, dass auf das Abrufen eines vollständigen Verweises auf Objekte verzichtet wird. (Dadurch wird es unmöglich, aktuelle Werte aus diesen Objekten abzurufen.)  
  
6. Aktivieren Sie die Anforderung mithilfe von <xref:System.Windows.Automation.CacheRequest.Activate%2A> innerhalb eines- `using` Blocks ( `Using` in Microsoft Visual Basic .net).  
  
 Deaktivieren Sie nach dem Abrufen von <xref:System.Windows.Automation.AutomationElement> -Objekten oder dem Abonnieren von Ereignissen die Anforderung, indem Sie <xref:System.Windows.Automation.CacheRequest.Pop%2A> verwenden (wenn <xref:System.Windows.Automation.CacheRequest.Push%2A> verwendet wurde) oder indem Sie das durch <xref:System.Windows.Automation.CacheRequest.Activate%2A>erstellte Objekt löschen. (Verwenden Sie <xref:System.Windows.Automation.CacheRequest.Activate%2A> in einem- `using` Block ( `Using` in Microsoft Visual Basic .net).  
  
### <a name="cache-automationelement-properties"></a>Zwischenspeichern von AutomationElement-Eigenschaften  
  
1. Während ein <xref:System.Windows.Automation.CacheRequest> aktiv ist, können Sie <xref:System.Windows.Automation.AutomationElement> -Objekte über <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> oder <xref:System.Windows.Automation.AutomationElement.FindAll%2A>abrufen. Sie können ein <xref:System.Windows.Automation.AutomationElement> -Objekt aber auch als Quelle eines Ereignisses abrufen, für das Sie eine Registrierung vorgenommen haben, als das <xref:System.Windows.Automation.CacheRequest> -Objekt aktiv war. (Sie können einen Cache auch erstellen, indem Sie ein <xref:System.Windows.Automation.CacheRequest> an GetUpdatedCache oder an eine der <xref:System.Windows.Automation.TreeWalker> -Methoden übergeben.)  
  
2. Verwenden Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> , oder rufen Sie eine Eigenschaft aus der <xref:System.Windows.Automation.AutomationElement.Cached%2A> -Eigenschaft des <xref:System.Windows.Automation.AutomationElement>-Objekts ab.  
  
### <a name="obtain-cached-patterns-and-their-properties"></a>Abrufen von zwischengespeicherten Mustern und deren Eigenschaften  
  
1. Während ein <xref:System.Windows.Automation.CacheRequest> aktiv ist, können Sie <xref:System.Windows.Automation.AutomationElement> -Objekte über <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> oder <xref:System.Windows.Automation.AutomationElement.FindAll%2A>abrufen. Sie können ein <xref:System.Windows.Automation.AutomationElement> -Objekt aber auch als Quelle eines Ereignisses abrufen, für das Sie eine Registrierung vorgenommen haben, als das <xref:System.Windows.Automation.CacheRequest> -Objekt aktiv war. (Sie können einen Cache auch erstellen, indem Sie ein <xref:System.Windows.Automation.CacheRequest> an GetUpdatedCache oder an eine der <xref:System.Windows.Automation.TreeWalker> -Methoden übergeben.)  
  
2. Verwenden Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> , um ein zwischengespeichertes Muster abzurufen.  
  
3. Rufen Sie Eigenschaftswerte aus der `Cached` -Eigenschaft des Steuerelementmusters ab.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden die verschiedenen Möglichkeiten des Zwischenspeicherns gezeigt. Dabei wird <xref:System.Windows.Automation.CacheRequest.Activate%2A> verwendet wird, um das <xref:System.Windows.Automation.CacheRequest>-Objekt zu aktivieren.  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden die verschiedenen Möglichkeiten des Zwischenspeicherns gezeigt. Dabei wird <xref:System.Windows.Automation.CacheRequest.Push%2A> verwendet wird, um das <xref:System.Windows.Automation.CacheRequest>-Objekt zu aktivieren. Sie sollten möglichst <xref:System.Windows.Automation.CacheRequest.Activate%2A>verwenden, es sei denn, Sie möchten Cacheanforderungen schachteln.  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](caching-in-ui-automation-clients.md)
