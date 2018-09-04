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
ms.openlocfilehash: 8a14b00fe762d325028072cd0ea3eecf9b9206e3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43538530"
---
# <a name="xstatic-markup-extension"></a>x:Statische Markuperweiterung
Verweist auf alle statischen by-Value-Codeentitäten, die in definiert ist eine [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– konforme Speicherung. Die statische Eigenschaft, die auf die verwiesen wird kann verwendet werden, um den Wert einer Eigenschaft in XAML bereitzustellen.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
| | |  
|-|-|  
|`prefix`|Dies ist optional. Ein Präfix, das mit einem zugeordneten, nicht standardmäßigen XAML-Namespace verweist. `prefix` wird explizit in der Verwendung angezeigt werden, da Sie selten Eigenschaften für statische verweisen, die von einem Standard-XAML-Namespace enthalten sind. Siehe Hinweise.|  
|`typeName`|Erforderlich. Der Name des Typs, der den gewünschten statischen Member definiert.|  
|`staticMemberName`|Erforderlich. Der Name des Members gewünschten statischen Wert (eine Konstante, eine statische Eigenschaft, eines Felds oder eines Enumerationswerts).|  
  
## <a name="remarks"></a>Hinweise  

Die Codeentität, die auf die verwiesen wird, muss eine der folgenden sein:  
  
-   Eine Konstante  
-   Eine statische Eigenschaft  
-   Ein Feld  
-   Ein Enumerationswert

Angeben einer beliebigen anderen Codeentität, z. B. eine nicht statische Eigenschaft bewirkt, dass einen Fehler während der Kompilierung ist die XAML-Markup kompiliert und eine XAML-Ladezeit-Analyseausnahme.  

Möglich `x:Static` Verweise auf statische Felder oder Eigenschaften, die nicht in der XAML-Standardnamespace für das aktuelle XAML-Dokument; dies erfordert jedoch eine Präfix-Zuordnung. XAML-Namespaces werden fast immer für das Stammelement des XAML-Dokuments definiert.  

Wenn sie mit der Standard-XAML-Schemakontext ausgeführt werden, können die Suchvorgänge für statische Eigenschaften von .NET Framework-XAML-Dienste und die XAML-Readern und XAML-Writer, ausgeführt werden. Dieser XAML-Schemakontext können CLR-Reflektion Graph objekterstellung notwendigen statische Werte bereit. Die `typeName` Sie angeben, ist tatsächlich ein XAML Typname, keine CLR-Typnamen, auch diese sind im Wesentlichen den gleichen Namen bei Verwendung den Standard-XAML-Schemakontext, oder wenn Sie alle vorhandenen CLR-basierten XAML-implementierungsframeworks verwenden.  

Vorsichtig, wenn Sie stellen `x:Static` Verweise, die nicht direkt der Typ des Werts einer Eigenschaft sind. In der XAML Verarbeitungssequenz, Werte von einer Markuperweiterung bereitgestellt werden nicht aufrufen, zusätzliche wertkonvertierung. Dies gilt auch, wenn Ihre `x:Static` Verweis erstellt eine Zeichenfolge, und eine wertkonvertierung für Attributwerte, die basierend auf Textzeichenfolge in der Regel tritt auf, für die dieses bestimmte Element oder für alle Memberwerte des Rückgabetyps.  

Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Static`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>-Erweiterungsklasse zugeordnet.  

Es gibt zwei anderen XAML-Verwendungen, die technisch möglich ist. Allerdings sind diese Verwendungen seltener auf, da sie unnötig ausführlich sind:  

1.  Die Objektelementsyntax.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2.  Attribut-Syntax mit expliziter Member-Eigenschaft für die Initialisierungszeichenfolge an.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

In der .NET Framework-XAML-Dienste-Implementierung, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.StaticExtension> Klasse.  

`x:Static` ist eine Markuperweiterung. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax, dies ist die Konvention mit dem ein XAML-Prozessor erkennt, dass eine Markuperweiterung einen Wert angeben, muss. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Der XAML-Standardnamespace, die Sie für WPF-Programmierung verwenden enthält viele nützliche statische Eigenschaften nicht, und die meisten nützlich statische Eigenschaften Unterstützung wie z. B. Typkonverter, die die Verwendung ohne erleichtern `{x:Static}` . Für statische Eigenschaften müssen Sie ein Präfix für einen XAML-Namespace zuordnen, wenn eine der folgenden Aussagen zutrifft:  
  
-   Sie verweisen auf einen Typ, die in WPF vorhanden ist, aber ist nicht Teil der XAML-Standardnamespace für WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). Dies ist ein gängiges Szenario für die Verwendung von `x:Static`. Können z. B. eine `x:Static` Verweis auf eine XAML-Namespace-Zuordnung zu den <xref:System> CLR-Namespace und Mscorlib-Assembly um die statischen Eigenschaften der verweisen die <xref:System.Environment> Klasse.  
  
-   Sie sind auf einen Typ aus einer benutzerdefinierten Assembly verweisen.  
  
-   Sie verweisen auf einen Typ, der in einer WPF-Assembly vorhanden ist, aber innerhalb eines CLR-Namespace ist, die nicht als Teil der WPF-XAML-Standardnamespace zugeordnet wurde. Die Zuordnung von CLR-Namespaces in der XAML-Standardnamespace für WPF von Definitionen in den verschiedenen WPF-Assemblys ausgeführt wird (Weitere Informationen zu diesem Konzept, finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Nicht zugeordnete CLR-Namespaces können vorhanden sein, wenn der CLR-Namespace besteht hauptsächlich aus Klassendefinitionen, die nicht in der Regel für XAML, wie z. B. <xref:System.Windows.Threading>.  
  
 Weitere Informationen zur Verwendung von Präfixen und Namespaces von XAML für WPF finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [x:Type-Markuperweiterung](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Aus WPF zu System.Xaml migrierte Typen](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
