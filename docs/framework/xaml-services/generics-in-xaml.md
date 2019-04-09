---
title: Generics in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9263edf18872f510f5f2f4e3e9cb793e45c5d0b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221599"
---
# <a name="generics-in-xaml"></a>Generics in XAML
Der .NET Framework-XAML-Dienste gemäß der Implementierung in "System.xaml" bietet Unterstützung für die Verwendung von generischen CLR-Typen. Diese Unterstützung umfasst, die Einschränkungen von Generika als Typargument angeben und die Durchsetzung der Einschränkung durch Aufrufen der entsprechenden `Add` Methode für die generische Auflistung von Fällen. In diesem Thema werden Aspekte der Verwendung von und verweisen auf generische Typen in XAML beschrieben.  
  
## <a name="xtypearguments"></a>x:TypeArguments  
 `x:TypeArguments` eine Richtlinie wird von der XAML-Sprache definiert werden. Wenn sie als Mitglied eines XAML-Typs verwendet wird, die von einem generischen Typ unterstützt wird `x:TypeArguments` Typargumente, übergibt das Einschränken der generischen an den Konstruktor für die Sicherung. Referenz-Syntax, die zu .NET Framework-XAML-Diensten gehört zu verwenden, der `x:TypeArguments`, wozu Syntaxbeispiele finden Sie unter [X: TypeArguments Directive](x-typearguments-directive.md).  
  
 Da `x:TypeArguments` nimmt eine Zeichenfolge, und sichern für Typ-Konverter, hat sie in der Regel in der XAML-Auslastung als Attribut deklariert ist.  
  
 Im XAML-Knotenstream, die Informationen deklariert werden, indem `x:TypeArguments` erhalten <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> an eine `StartObject` Position im Knotenstream. Der Rückgabewert von <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> ist eine Liste der <xref:System.Xaml.XamlType> Werte. Bestimmung der gibt an, ob ein XAML-Typ für einen generischen Typ darstellt kann vorgenommen werden, durch den Aufruf <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Regeln und Syntaxkonventionen für Generika in XAML  
 In XAML muss ein generischer Typ immer als eine eingeschränkte generische dargestellt werden; ein generischer uneingeschränkte nie in das XAML-Typsystem oder einem XAML-Knotenstream vorhanden ist und nicht in XAML-Markup dargestellt werden. Eine generische kann in XAML-Attributsyntax für Fälle, in denen es ist ein geschachtelter typeinschränkung eines generischen verweist auf die, verwiesen werden `x:TypeArguments`, oder für Fälle, in denen `x:Type` stellt einen CLR-Typ-Verweis für einen generischen Typ. Dies wird unterstützt, über die <xref:System.Xaml.Schema.XamlTypeTypeConverter> von .NET Framework-XAML-Diensten definierte Klasse.  
  
 Der XAML-Attribut aktiviert, indem Syntaxformat <xref:System.Xaml.Schema.XamlTypeTypeConverter> ändert die typische MSIL / CLR-Syntax-Konvention, die Spitzen verwendet eckige Klammern für Typen und Einschränkungen von Generika und stattdessen ersetzt Klammern für den Container für die Einschränkung. Ein Beispiel finden Sie unter [X: TypeArguments Directive](x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Generika und XAML 2009-Funktionen  
 Wenn Sie XAML 2009 verwenden anstelle von mapping des CLR-Basistypen zum Abrufen von XAML-Typen für häufige Sprachprimitive, können Sie [integrierte Typen für XAML 2009](built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in `x:TypeArguments`. Sie können z. B. die folgenden deklarieren (Präfix-Zuordnungen, die nicht angezeigt, aber `x` ist der XAML-Sprachnamespace XAML für XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Generikunterstützung in WPF und anderen Frameworks v3. 5  
 Für die XAML 2006-Verwendung, wenn speziell auf WPF abzielen [X: Class](x-class-directive.md) muss auch angegeben werden, auf das gleiche Element wie `x:TypeArguments`, dieses Element muss das Stammelement in einem XAML-Dokument. Das Stammelement muss auf einen generischen Typ mit mindestens einem Typargument zugeordnet. Ein Beispiel hierfür ist <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Mögliche problemumgehungen für allgemeine Verwendungen zu unterstützen sind, definieren eine benutzerdefinierte Markuperweiterung, die generische Typen zurückgeben kann, oder einen Vorschub bereitstellen Definition, die aus einem generischen Typ abgeleitet ist, aber vereinfacht die generische Einschränkung in ihrer eigenen Klassendefinition der Klasse.  
  
 In WPF und Zielgruppenadressierung [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments`, jedoch nur für loose XAML (XAML, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.  
  
 Benutzerdefinierte Workflows in Windows Workflow Foundation für [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] generischen XAML-Verwendung nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [x:TypeArguments-Anweisung](x-typearguments-directive.md)
- [x:Class-Direktive](x-class-directive.md)
- [Integrierte Typen für häufige XAML-Sprachprimitive](built-in-types-for-common-xaml-language-primitives.md)
