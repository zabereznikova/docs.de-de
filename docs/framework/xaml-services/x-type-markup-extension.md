---
title: x:Type-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: df0b3fe53cb8f284fc6e2d79a9b2cea86318d701
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459911"
---
# <a name="xtype-markup-extension"></a>x:Type-Markuperweiterung
Stellt das CLR-<xref:System.Type> Objekt bereit, das der zugrunde liegende Typ für einen angegebenen XAML-Typ ist.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`prefix`|Dies ist optional. Ein Präfix, das einen nicht standardmäßigen XAML-Namespace zuordnet. Die Angabe eines Präfixes ist häufig nicht erforderlich. Siehe Hinweise.|  
|`typeNameValue`|Erforderlich. Ein Typname, der zum aktuellen XAML-Standard Namespace aufgelöst werden konnte. oder das angegebene zugeordnete Präfix, wenn `prefix` angegeben wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `x:Type` Markup Erweiterung hat eine ähnliche Funktion wie der `typeof()`-Operator C# in oder der `GetType`-Operator in Microsoft Visual Basic.  
  
 Die `x:Type` Markup Erweiterung liefert ein Zeichen folgen-Konvertierungs Verhalten für Eigenschaften, die den Typ <xref:System.Type>annehmen. Die Eingabe ist ein XAML-Typ. Die Beziehung zwischen dem Eingabe-XAML-Typ und der Ausgabe-CLR <xref:System.Type> besteht darin, dass die Ausgabe <xref:System.Type> der <xref:System.Xaml.XamlType.UnderlyingType%2A> der Eingabe <xref:System.Xaml.XamlType>ist, nachdem die erforderlichen <xref:System.Xaml.XamlType> basierend auf dem XAML-Schema Kontext und dem <xref:System.Windows.Markup.IXamlTypeResolver> Dienst, den der Kontext bereitstellt, nach sucht wurden.  
  
 In .NET Framework XAML-Diensten wird die Behandlung dieser Markup Erweiterung durch die <xref:System.Windows.Markup.TypeExtension>-Klasse definiert.  
  
 In bestimmten Framework-Implementierungen können einige Eigenschaften, die <xref:System.Type> als Wert annehmen, den Namen des Typs direkt akzeptieren (der Zeichen folgen Wert des Typs `Name`). Das Implementieren dieses Verhaltens ist jedoch ein komplexes Szenario. Beispiele hierzu finden Sie im folgenden Abschnitt "WPF-Verwendungs Hinweise".  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Type`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.TypeExtension.TypeName%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.TypeExtension>-Erweiterungsklasse zugeordnet. Im standardmäßigen XAML-Schema Kontext für .NET Framework XAML-Dienste, die auf CLR-Typen basieren, ist der Wert dieses Attributs entweder der <xref:System.Reflection.MemberInfo.Name%2A> des gewünschten Typs oder enthält <xref:System.Reflection.MemberInfo.Name%2A>, dem ein Präfix für eine nicht standardmäßige XAML-Namespace Zuordnung vorangestellt ist.  
  
 Die `x:Type` Markup Erweiterung kann in der Objekt Element Syntax verwendet werden. In diesem Fall ist die Angabe des Werts der <xref:System.Windows.Markup.TypeExtension.TypeName%2A> Eigenschaft erforderlich, um die Erweiterung ordnungsgemäß zu initialisieren.  
  
 Die `x:Type` Markup Erweiterung kann auch als ausführliche-Attribut verwendet werden. Diese Verwendung ist jedoch nicht typisch: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>XAML-Standard Namespace und-Typzuordnung  
 Der XAML-Standard Namespace für die WPF-Programmierung enthält die meisten XAML-Typen, die Sie für typische XAML-Szenarien benötigen. Daher können Sie beim Verweis auf XAML-Typwerte häufig Präfixe vermeiden. Möglicherweise müssen Sie ein Präfix zuordnen, wenn Sie auf einen Typ aus einer benutzerdefinierten Assembly oder auf Typen verweisen, die in einer WPF-Assembly vorhanden sind, aber von einem CLR-Namespace stammen, der nicht dem standardmäßigen XAML-Namespace zugeordnet wurde. Weitere Informationen zu Präfixen, XAML-Namespaces und zum Mapping von CLR-Namespaces finden Sie unter [XAML-Namespaces und Namespace Zuordnung für WPF-XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Typeigenschaften, die "tytzame-As-String" unterstützen  
 WPF unterstützt Techniken, mit denen der Wert einiger Eigenschaften vom Typ <xref:System.Type> angegeben werden kann, ohne dass eine `x:Type` Markup Erweiterungs Verwendung erforderlich ist. Stattdessen können Sie den Wert als Zeichenfolge angeben, die den Typ benennt. Beispiele hierfür sind <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> und <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Unterstützung für dieses Verhalten wird nicht durch Typkonverter oder Markup Erweiterungen bereitgestellt. Stattdessen handelt es sich hierbei um ein Verzögerungs Verhalten, das über <xref:System.Windows.FrameworkElementFactory>implementiert wird.  
  
 Silverlight unterstützt eine ähnliche Konvention. Tatsächlich unterstützt Silverlight derzeit keine `{x:Type}` in der XAML-Sprachunterstützung und akzeptiert keine `{x:Type}` Verwendung außerhalb einiger Umstände, die zur Unterstützung der WPF-Silverlight-XAML-Migration vorgesehen sind. Daher ist das Verhalten von "tytzame-As-String" in alle Eigenschafts Auswertungs Eigenschaften von Silverlight integriert, wobei ein <xref:System.Type> der Wert ist.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 bietet zusätzliche Unterstützung für generische Typen und ändert das Funktionsverhalten von `x:TypeArguments` und `x:Type`, um diese Unterstützung bereitzustellen.  
  
- `x:TypeArguments` und das zugeordnete Objekt Element für eine generische Objekt Instanziierung können sich auf anderen Elementen als dem Stamm Element befinden. Weitere Informationen finden Sie im Abschnitt "XAML 2009" der [x:TypeArguments-Direktive](x-typearguments-directive.md).  
  
- XAML 2009 unterstützt eine Syntax zum Angeben der Einschränkung eines generischen Typs in Markup. Dies kann `x:TypeArguments`, `x:Type`oder die beiden Features in Kombination verwendet werden.  
  
- Bei der WPF-XAML-Implementierung bei der Verarbeitung von XAML 2009 für Load wird diese Funktion auch dem impliziten Typkonvertierungs Verhalten für bestimmte Framework-Eigenschaften hinzugefügt, die Type <xref:System.Type>verwenden.  
  
 In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für Loose XAML (XAML, das nicht Markup kompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Style>
- [Erstellen von Formaten und Vorlagen](../wpf/controls/styling-and-templating.md)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
