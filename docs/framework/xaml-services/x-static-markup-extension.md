---
title: x:Statische Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: 980bf6a1bdb19afd5c8d3c798d31037ab8cd7086
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565574"
---
# <a name="xstatic-markup-extension"></a>x:Statische Markuperweiterung
Verweist auf eine statische per-Wert-Code-Entität, die in definiert ist eine [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– kompatible Weise. Die statische Eigenschaft, auf die verwiesen wird, kann, geben Sie den Wert einer Eigenschaft in XAML verwendet werden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`prefix`|Dies ist optional. Ein Präfix, das auf einem zugeordneten, nicht standardmäßigen XAML-Namespace verweist. `prefix` wird explizit in der Verwendung angezeigt werden, da Sie selten statische Eigenschaften verweisen, die von einer standardmäßigen XAML-Namespace stammen. Siehe Hinweise.|  
|`typeName`|Erforderlich. Der Name des Typs, der den gewünschten statischen Member definiert.|  
|`staticMemberName`|Erforderlich. Der Name des Members gewünschten statischen Wert (eine Konstante, eine statische Eigenschaft, ein Feld oder ein Enumerationswert).|  
  
## <a name="remarks"></a>Hinweise  
 Die Codeentität, auf die verwiesen wird, muss eine der folgenden sein:  
  
-   Eine Konstante  
  
-   Eine statische Eigenschaft  
  
-   Ein Feld  
  
-   Ein Enumerationswert  
  
 Alle anderen Entitäten in einem Code, z. B. eine nicht statische Eigenschaft angeben bewirkt, dass einen Fehler während der Kompilierung der XAML-Code ist Markupkompilierung oder eine Verwendung von XAML-Analyse Ladezeit-Ausnahme.  
  
 Sie können vornehmen `x:Static` Verweise auf statische Felder oder Eigenschaften, die nicht in der standardmäßigen XAML-Namespace für das aktuelle XAML-Dokument; sind allerdings erfordert dies eine/Präfix-Zuordnung. Verwendung von XAML-Namespaces werden fast immer für das Stammelement des XAML-Dokuments definiert.  
  
 Wenn sie mit der Verwendung von XAML-Standardschemakontext ausgeführt werden, können die Suchvorgänge für statischen Eigenschaften von .NET Framework-XAML-Dienste und die XAML-Readern und XAML-Writern ausgeführt werden. Dieser XAML-Schemakontext können CLR-Reflektion Graph Objektkonstruktion die notwendigen statische Werte bereit. Die `typeName` Sie angeben, ist tatsächlich eine XAML-Typnamen, keinen CLR-Typnamen, obwohl es sich bei der Verwendung von XAML-Standardschemakontext verwenden, oder wenn alle vorhandenen CLR-basierten XAML-implementierungsframeworks verwendet im Wesentlichen die gleichen Namen handelt.  
  
 Gehen Sie vorsichtig vor, wenn Sie machen `x:Static` Verweise, die nicht direkt der Typ des Werts einer Eigenschaft sind. In der XAML-Code Bearbeitungssequenz bereitgestellten Werte aus einer Markuperweiterung nicht aufrufen, Leistungsumfang Konvertierung. Dies gilt auch dann, wenn Ihre `x:Static` Verweis erstellt eine Textzeichenfolge und eine Wert-Konvertierung für Attributwerte, die in der Regel anhand der Textzeichenfolge auftritt, für dieses bestimmte Element oder für eine beliebige Memberwerte des Rückgabetyps.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Static`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>-Erweiterungsklasse zugeordnet.  
  
 Es gibt zwei XAML-Verwendungen, die technisch möglich sind. Allerdings sind diese Verwendungen ungewöhnlich, da sie unnötig detailliert sind:  
  
 **Syntax der Object-Element:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`  
  
 **Die Attributsyntax mit expliziten Elementeigenschaft für Initialisierungszeichenfolge:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`  
  
 In der .NET Framework-XAML-Dienste-Implementierung wird durch die Verarbeitung für diese Markuperweiterung definiert die <xref:System.Windows.Markup.StaticExtension> Klasse.  
  
 `x:Static` ist eine Markuperweiterung. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax normalerweise wird mit dem ein XAML-Prozessor erkennt, dass eine Markuperweiterung einen Wert bereitstellen muss. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Die standardmäßigen XAML-Namespace, die Sie, für die WPF-Programmierung verwenden enthält keine viele nützliche statische Eigenschaften, und Großteil der nützlichen statischen Eigenschaften haben Unterstützung z. B. Typkonverter, die die Verwendung ohne erleichtern `{x:Static}` . Für statische Eigenschaften müssen Sie ein Präfix für einen XAML-Namespace zuordnen, wenn eine der folgenden Aussagen zutrifft:  
  
-   Sie sind einen Typ, der im WPF vorhanden, aber ist nicht Teil der XAML-Standardnamespace für WPF verweisen ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). Dies ist ein gängiges Szenario für die Verwendung von `x:Static`. Können z. B. ein `x:Static` Verweis mit einer XAML-Namespacezuordnung an die <xref:System> CLR-Namespace und Mscorlib-Assembly um die statischen Eigenschaften der verweisen die <xref:System.Environment> Klasse.  
  
-   Sie werden einen Typ aus einer benutzerdefinierten Assembly verweisen.  
  
-   Sie sind einen Typ, der in einer WPF-Assembly vorhanden ist verweisen, aber dieser Typ innerhalb eines CLR-Namespace ist, die nicht als Teil der WPF-XAML-Standardnamespace zugeordnet wurde. Die Zuordnung des CLR-Namespaces in der XAML-Standardnamespace für WPF wird von Definitionen in den verschiedenen WPF-Assemblys ausgeführt (Weitere Informationen zu diesem Konzept finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Nicht zugeordnete CLR-Namespaces kann vorhanden sein, wenn der CLR-Namespace besteht hauptsächlich aus Klassendefinitionen, die nicht in der Regel für XAML, wie z. B. <xref:System.Windows.Threading>.  
  
 Weitere Informationen zur Verwendung von Präfixen und XAML-Namespaces für WPF finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [x:Type-Markuperweiterung](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Aus WPF zu System.Xaml migrierte Typen](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
