---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614617"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>Ändern eines Primärschlüssels durch WPF beim Anzeigen von ADO-Daten in einem Master/Detail-Szenario

#### <a name="details"></a>Details

Nehmen Sie an, Sie haben eine ADO-Sammlung von Elementen des Typs `Order` mit einer Beziehung namens &quot;OrderDetails&quot;, durch die diese Sammlung über den Primärschlüssel &quot;OrderID&quot; mit einer Sammlung von Elementen des Typs `Detail` verknüpft wird. In Ihrer WPF-App können Sie ein Listensteuerelement an die Details für einen bestimmten Auftrag binden:

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

Beim DataContext handelt es sich um ein `Order`-Element. WPF ruft den Wert der Eigenschaft `OrderDetails` ab. Es handelt sich hierbei um eine D-Sammlung aller `Detail`-Elemente, deren `OrderID` der `OrderID` des Masterelements entspricht. Der Behavior Change wird angezeigt, wenn Sie den Primärschlüssel `OrderID` des Masterelements ändern. ADO ändert automatisch die `OrderID` jedes der betroffenen Datensätze in der Sammlung „Details“ (also diejenigen, die in Sammlung D kopiert wurden).  Was passiert mit D?

- Altes Verhalten: Sammlung D wird gelöscht. Das Masterelement löst *keine* Änderungsbenachrichtigung für die Eigenschaft `OrderDetails` aus. Das ListBox-Element verwendet weiterhin Sammlung D, die jetzt leer ist.
- Neues Verhalten:  Sammlung D wird nicht geändert. Jedes enthaltene Element löst Änderungsbenachrichtigung für die Eigenschaft `OrderID` aus. ListBox verwendet weiterhin Sammlung D, und zeigt die Details mit der neuen `OrderID` an. WPF implementiert das neue Verhalten, indem Sammlung D auf andere Weise erstellt wird: durch Aufruf der ADO-Methode <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> mit dem auf `true` festgelegten `followParent`-Argument.

#### <a name="suggestion"></a>Vorschlag

Eine App ruft das neue Verhalten durch Verwendung der folgenden AppContext-Option auf.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

Die Option ist für Apps, die auf .NET 4.7.1 oder niedriger ausgelegt sind, standardmäßig auf `true` festgelegt (altes Verhalten). Für Apps, die auf .NET 4.7.2 oder höher ausgelegt sind, ist sie standardmäßig auf `false` festgelegt.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
