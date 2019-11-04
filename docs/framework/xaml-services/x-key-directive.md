---
title: x:Key-Anweisung
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: b00218623add052e135bc5815d615fe7cdf002ee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459960"
---
# <a name="xkey-directive"></a>x:Key-Anweisung
Kennzeichnet Elemente eindeutig, die in einem XAML-definierten Wörterbuch erstellt und referenziert werden. Einem XAML-Objektelement einen `x:Key`-Wert hinzuzufügen, ist der üblichste Weg, um eine Ressource in einem Ressourcenwörterbuch, beispielsweise in einem WPF- <xref:System.Windows.ResourceDictionary> zu identifizieren.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Verwendung von XAML-Attributen (WPF-spezifisch)  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`stringKeyValue`|Eine Textzeichenfolge, die als Schlüssel verwendet werden soll. Die Text Zeichenfolge muss der [XamlName-Grammatik](xamlname-grammar.md)entsprechen.|  
|`markupExtensionUsage`|Innerhalb der Markup Erweiterungs Trennzeichen {}eine Markup Erweiterungs Verwendung, die ein Objekt bereitstellt, das als Schlüssel verwendet werden soll. Siehe Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 `x:Key` unterstützt das XAML-Ressourcenwörterbuchkonzept. XAML als Sprache definiert keine Ressourcenwörterbuchimplementierung, die spezifischen Benutzeroberflächen-Frameworks vorbehalten bleibt. Weitere Informationen dazu, wie XAML-Ressourcen Wörterbücher in WPF implementiert werden, finden Sie unter [XAML-Ressourcen](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 In XAML 2006 und WPF müssen `x:Key` als Attribut bereitgestellt werden. Sie können immer noch Nichtzeichenfolgeschlüssel verwenden, aber dies erfordert eine Markuperweiterungsverwendung, um den Nichtzeichenfolgenwert in Attributform bereitzustellen. Wenn Sie XAML 2009 verwenden, kann `x:Key` als-Element angegeben werden, um explizit von anderen Objekttypen als Zeichen folgen verschlüsselte Wörter zu unterstützen, ohne dass eine Markup Erweiterung erforderlich ist. Weitere Informationen finden Sie im Abschnitt "XAML 2009" in diesem Thema. Der Rest des Abschnitts "Hinweise" bezieht sich speziell auf die XAML 2006-Implementierung.  
  
 Der-Attribut Wert von `x:Key` kann eine beliebige Zeichenfolge sein, die in der [XamlName-Grammatik](xamlname-grammar.md) definiert ist, oder ein Objekt, das durch eine Markup Erweiterung ausgewertet wird. Ein Beispiel aus WPF finden Sie unter "Hinweise zur WPF-Verwendung".  
  
 Untergeordnete Elemente eines übergeordneten Elements, bei dem es sich um eine <xref:System.Collections.IDictionary>-Implementierung handelt, müssen im Allgemeinen ein `x:Key`-Attribut enthalten, das einen eindeutigen Schlüsselwert in diesem Wörterbuch angibt. Frameworks könnten als Alias definierte Schlüsseleigenschaften implementieren, um `x:Key` bei bestimmten Typen zu vertreten; Typen, die solche Eigenschaften definieren, sollten mit dem Attribut <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> versehen werden.  
  
 Das Codeäquivalent zum Festlegen von `x:Key` ist der Schlüssel, wie er für den zugrunde liegenden <xref:System.Collections.IDictionary> verwendet wird. So entspricht z. B. ein im Markup für eine Ressource in WPF angewendeter `x:Key` dem Wert des `key`-Parameters von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>, wenn Sie die Ressource einem WPF <xref:System.Windows.ResourceDictionary> im Code hinzufügen.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Untergeordnete Objekte eines übergeordneten Objekts, bei dem es sich um eine <xref:System.Collections.IDictionary>-Implementierung wie z. B. WPF <xref:System.Windows.ResourceDictionary> handelt, müssen im Allgemeinen ein `x:Key`-Attribut enthalten, und der Schlüsselwert muss in diesem Wörterbuch eindeutig sein. Dabei gelten zwei wichtige Ausnahmen:  
  
- Einige WPF-Typen deklarieren einen impliziten Schlüssel für Wörterbuchverwendung. Zum Beispiel kann sich ein <xref:System.Windows.Style> mit einem <xref:System.Windows.Style.TargetType%2A> oder ein <xref:System.Windows.DataTemplate> mit einem <xref:System.Windows.DataTemplate.DataType%2A> in einem <xref:System.Windows.ResourceDictionary> befinden und den impliziten Schlüssel verwenden.  
  
- WPF unterstützt das Konzept zusammengeführter Ressourcenwörterbücher. Schlüssel können zwischen den zusammengeführten Wörterbüchern freigegeben sein, und auf das Verhalten der freigegebenen Schlüssel kann mit <xref:System.Windows.FrameworkContentElement.FindResource%2A> zugegriffen werden. Weitere Informationen finden Sie unter [Zusammengeführte Ressourcenverzeichnisse](../wpf/advanced/merged-resource-dictionaries.md).  
  
 In der gesamten WPF-XAML-Implementierung und im Anwendungsmodell wird die Eindeutigkeit der Schlüssel nicht vom XAML-Markupcompiler überprüft. Stattdessen führen fehlende oder nicht eindeutige `x:Key`-Werte zu XAML-Parser-Ladezeitfehlern. Die Visual Studio-Behandlung von Wörterbüchern für WPF kann jedoch häufig solche Fehler in der Entwurfsphase bemerken.  
  
 Beachten Sie, dass in der angegebenen Syntax bei der Erzeugung einer Auflistung durch den WPF-XAML-Prozessor, um eine <xref:System.Windows.ResourceDictionary>-Auflistung aufzufüllen, das <xref:System.Windows.FrameworkElement.Resources%2A>-Objekt implizit ist. Ein <xref:System.Windows.ResourceDictionary> wird in der Regel nicht explizit als Element im Markup bereitgestellt, obwohl dies in einigen Fällen aus Gründen der Anschaulichkeit möglich ist (hierbei würde es sich um ein Eigenschaftenelement der Auflistung zwischen dem <xref:System.Windows.FrameworkElement.Resources%2A>-Eigenschaftenelement und den darin enthaltenen Elementen handeln, von denen das Wörterbuch gefüllt wird). Informationen dazu, warum ein Auflistungs Objekt fast immer ein implizites Element im Markup ist, finden Sie [in der XAML-Syntax im Detail](../wpf/advanced/xaml-syntax-in-detail.md).  
  
 In der WPF XAML-Implementierung wird die Handhabung von Ressourcenwörterbuchschlüsseln durch die abstrakte <xref:System.Windows.ResourceKey>-Klasse definiert. Der WPF-XAML-Prozessor erstellt jedoch je nach ihrer Verwendung unterschiedliche zugrunde liegende Erweiterungstypen für Schlüssel. So wird z. B. der Schlüssel für <xref:System.Windows.DataTemplate> oder abgeleitete Klassen getrennt verarbeitet, und er erstellt ein anderes <xref:System.Windows.DataTemplateKey>-Objekt.  
  
 Schlüssel und Namen verwenden unterschiedliche Direktiven und Sprachelemente (`x:Key` gegenüber `x:Name`) in der grundlegenden XAML-Definition. Schlüssel und Namen werden auch in unterschiedlichen Situationen von der WPF-Definition und Anwendung dieser Konzepte genutzt. Weitere Informationen finden Sie unter [WPF-XAML-Namescopes](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Wie zuvor angegeben, kann der Wert eines Schlüssels durch eine Markuperweiterung angegeben werden und braucht kein Zeichenfolgenwert zu sein. Ein Beispiel für ein WPF-Szenario ist, dass der Wert von `x:Key` ein " [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md)" sein kann. Bestimmte Steuerelemente machen einen Stilschlüssel dieses Typs verfügbar, mit dem eine benutzerdefinierte Stilressource erstellt werden kann, die einen Teil des Aussehens und Verhaltens dieses Steuerelements beeinflusst, ohne den Stil vollständig zu ersetzen. Ein Beispiel für einen solchen Schlüssel ist <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 Die zusammengeführte Wörterbuchfunktion von WPF führt weitere Überlegungen zur Schlüsseleindeutigkeit und zum Schlüsselsuchverhalten ein. Weitere Informationen finden Sie unter [Zusammengeführte Ressourcenverzeichnisse](../wpf/advanced/merged-resource-dictionaries.md).  
  
## <a name="xaml-2009"></a>XAML 2009  
 Mit XAML 2009 wird die Einschränkung entspannt, dass `x:Key` immer in Attribut Form bereitgestellt werden.  
  
 In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht Markup kompiliert ist. Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.  
  
 Unter XAML 2009 können Sie `x:Key` Elemente mithilfe der folgenden Syntax angeben:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML-Elementverwendung (nur XAML 2009)  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`keyObject`|Objektelement für das Objekt, das für ein angegebenes `object` in einem spezialisierten Wörterbuch als Schlüssel verwendet wird.|  
  
- Der Container/das übergeordnete Element für diesen Typ der Verwendung wird hier nicht angezeigt. `object` wird erwartungsgemäß ein untergeordnetes Element eines Objektelements sein, das eine spezialisierte Wörterbuchimplementierung darstellt. `keyObject` ist erwartungsgemäß eine Objektinstanz (oder ein Wert eines Werttyps), die als Schlüssel für diese bestimmte spezialisierte Wörterbuchimplementierung geeignet ist.  
  
- WPF implementiert keine Wörterbücher, die diese Verwendung erfordern. Objektschlüssel sind eine allgemeinere Funktion der XAML-Sprache. Sie sind möglicherweise nützlich für bestimmte Benutzerwörterbuchszenarien, in denen das Erstellen des Wörterbuchs in XAML wünschenswert ist. Bei WPF-Funktionen, wie beispielsweise impliziten Stilen, die für Ressourcen Schlüssel verwenden, die keine Zeichenfolgen sind, gibt es andere Techniken für das Festlegen oder das Angeben der Schlüssel. Deshalb ist es nicht notwendig, einen Objektschlüssel zu verwenden.  
  
- bei " *keyObject* " kann es sich auch um eine Markup Erweiterungs Verwendung im Objekt Element Formular anstelle einer direkten Objektinstanz handeln.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Key` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:). Sprach Features (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ressourcen und Code](../wpf/advanced/resources-and-code.md)
- [StaticResource-Markuperweiterung](../wpf/advanced/staticresource-markup-extension.md)
