---
title: Generika in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: faef74c57ac5ff9e3d4162accfc6552db55715bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generics-in-xaml"></a>Generika in XAML
.NET Framework XAML Services wie in "System.xaml" implementiert bietet Unterstützung für die Verwendung von generischer CLR-Typen. Diese Unterstützung umfasst, die Einschränkungen von Generika als Typargument angeben und erzwingen die Einschränkung durch Aufrufen der entsprechenden `Add` Methode für die generische Auflistung von Fällen. In diesem Thema werden Aspekte der Verwendung von und verweisen auf generische Typen in XAML beschrieben.  
  
## <a name="xtypearguments"></a>X: TypeArguments-  
 `x:TypeArguments` eine Richtlinie wird durch die Verwendung von XAML-Sprache definiert werden. Wenn sie als Mitglied einer XAML-Typ verwendet wird, der einen generischen Typ verarbeitet `x:TypeArguments` übergibt einschränken Typargumente der generischen an den Konstruktor sichern. Referenz-Syntax, die auf .NET Framework XAML Services beziehen nutzen `x:TypeArguments`, inklusive der Syntaxbeispiele, finden Sie unter [X: TypeArguments-Direktive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Da `x:TypeArguments` akzeptiert eine Zeichenfolge und dahinter liegende Typ-Konverter, hat er in der Regel in XAML-Verwendung als Attribut deklariert ist.  
  
 In der XAML-Knotenstream deklariert die Informationen von `x:TypeArguments` abgerufen werden kann, aus <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> an eine `StartObject` Position im Knotenstream. Der Rückgabewert der <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> ist eine Liste von <xref:System.Xaml.XamlType> Werte. Bestimmung, ob ein XAML-Typ für einen generischen Typ darstellt, kann durch Aufrufen vorgenommen werden <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Regeln und Syntaxkonventionen für Generika in XAML  
 In XAML muss ein generischer Typ immer als eingeschränkte generische dargestellt werden; ein uneingeschränkter generischer nie in das XAML-Typsystem oder einem XAML-Knotenstream vorhanden ist und nicht in XAML-Markup dargestellt werden. Eine generische verwiesen werden kann, im XAML-Attributsyntax für Fälle, in dem es eine Einschränkung geschachtelter Typ einer Generika, indem Sie auf das verwiesen wird `x:TypeArguments`, oder in Fällen, in denen `x:Type` einen CLR-Typ-Verweis für einen generischen Typ bereitstellt. Dies wird unterstützt, über die <xref:System.Xaml.Schema.XamlTypeTypeConverter> Klasse durch .NET Framework XAML Services definiert.  
  
 Der XAML-Code-Attribut Syntaxformat aktivierte <xref:System.Xaml.Schema.XamlTypeTypeConverter> ändert die typische MSIL / CLR Syntax Konvention, die Spitze verwendet für Typen und Einschränkungen von Generika Klammern und Klammern für den Container Einschränkung stattdessen ersetzt. Ein Beispiel finden Sie unter [X: TypeArguments-Direktive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Generika und XAML 2009-Funktionen  
 Bei Verwendung von XAML 2009 anstelle von mapping des CLR-Basistypen um XAML-Typen für häufige Sprachprimitive zu erhalten, können Sie [integrierte XAML 2009-Typen](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) als Informationselementen in `x:TypeArguments`. Beispielsweise konnten Sie die folgenden deklarieren (Präfix-Zuordnungen, die nicht angezeigt, aber `x` ist die Verwendung von XAML-Verwendung von XAML-Sprachnamespace für XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Generikunterstützung in WPF und andere v3. 5-Frameworks  
 Für XAML 2006-Nutzung bei ausdrücklich auf WPF abzielen [X: Class](../../../docs/framework/xaml-services/x-class-directive.md) muss auch angegeben werden, auf demselben Element wie `x:TypeArguments`, und dieses Element muss das Stammelement in einem XAML-Dokument. Das Stammelement muss ein generischer Typ mit mindestens einem Typargument zuordnen. Ein Beispiel ist <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Mögliche problemumgehungen zur Unterstützung von generischen Verwendungen einschließen, definieren eine benutzerdefinierte Markuperweiterung, die generische Typen zurückgeben oder Bereitstellen einer Wrapping Klassendefinition, die aus einem generischen Typ abgeleitet wird, aber vereinfacht die generische Einschränkung in einem eigenen Klassendefinition.  
  
 In WPF und Zielgruppenadressierung [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments`, jedoch nur für loose XAML (, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.  
  
 Benutzerdefinierte Workflows in Windows Workflow Foundation [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] generische XAML-Verwendung nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [x:TypeArguments-Anweisung](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [x:Class-Anweisung](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
