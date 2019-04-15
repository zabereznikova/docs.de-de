---
ms.openlocfilehash: 2cd107dc92fd0fae89717c38840ce7ea44f3ac9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59233949"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>Ändern eines Primärschlüssels durch WPF beim Anzeigen von ADO-Daten in einem Master/Detail-Szenario

|   |   |
|---|---|
|Details|Nehmen Sie an, Sie haben eine ADO-Sammlung von Elementen des Typs <code>Order</code> mit einer Beziehung namens &quot;OrderDetails&quot;, durch die diese Sammlung über den Primärschlüssel &quot;OrderID&quot; mit einer Sammlung von Elementen des Typs <code>Detail</code> verknüpft wird. In Ihrer WPF-App können Sie ein Listensteuerelement an die Details für einen bestimmten Auftrag binden:<pre><code class="lang-xml">&lt;ListBox ItemsSource=&quot;{Binding Path=OrderDetails}&quot; &gt;&#13;&#10;</code></pre>Beim DataContext handelt es sich um ein <code>Order</code>-Element. WPF ruft den Wert der <code>OrderDetails</code>-Eigenschaft ab – eine Sammlung D aller <code>Detail</code>-Elemente, deren <code>OrderID</code> der <code>OrderID</code> des Masterelements entspricht. Die Verhaltensänderung tritt auf, wenn Sie den Primärschlüssel <code>OrderID</code> des Masterelements ändern. ADO ändert automatisch die <code>OrderID</code> jedes der betroffenen Datensätze in der Sammlung „Details“ (also diejenigen, die in Sammlung D kopiert wurden).  Was passiert mit D?<ul><li>Altes Verhalten:   Sammlung D wird gelöscht.   Das Masterelement löst <em>keine</em> Änderungsbenachrichtigung für die Eigenschaft <code>OrderDetails</code> aus.  Das ListBox-Element verwendet weiterhin Sammlung D, die jetzt leer ist.</li><li>Neues Verhalten:  Sammlung D wird nicht geändert.   Jedes enthaltene Element löst Änderungsbenachrichtigung für die Eigenschaft <code>OrderID</code> aus.  ListBox verwendet weiterhin Sammlung D, und zeigt die Details mit der neuen <code>OrderID</code> an.</li></ul>WPF implementiert das neue Verhalten, indem Sammlung D auf andere Weise erstellt wird: durch Aufruf der ADO-Methode <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> mit dem auf <code>true</code> festgelegten <code>followParent</code>-Argument.|
|Vorschlag|Eine App ruft das neue Verhalten durch Verwendung der folgenden AppContext-Option auf.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;&#13;&#10;</code></pre>Die Option ist für Apps, die auf .NET 4.7.1 oder niedriger ausgelegt sind, standardmäßig auf <code>true</code> festgelegt (altes Verhalten). Für Apps, die auf .NET 4.7.2 oder höher ausgelegt sind, ist sie standardmäßig auf <code>false</code> festgelegt.|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Neuzuweisung|
