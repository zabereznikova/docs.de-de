---
title: "Generics in XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "generics [XAML Services]"
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Generics in XAML
Die in "System.Xaml" implementierten .NET Framework\-XAML\-Dienste bieten Unterstützung für die Verwendung generischer CLR\-Typen.  Diese Unterstützung umfasst das Angeben der Einschränkungen der Generika als Typargument und das Erzwingen der Einschränkung durch das Aufrufen der entsprechenden `Add`\-Methode für generische Auflistungsfälle.  In diesem Thema werden Aspekte der Verwendung von generischen Typen und des Verweisens auf generische Typen in XAML beschrieben.  
  
## x:TypeArguments  
 `x:TypeArguments` ist eine durch die XAML\-Sprache definierte Direktive.  Bei Verwendung als Member eines XAML\-Typs, der von einem generischen Typ unterstützt wird, übergibt `x:TypeArguments` einschränkende Typargumente vom generischen an den unterstützenden Konstruktor.  Die Verweissyntax für die Verwendung von `x:TypeArguments` in .NET Framework\-XAML\-Diensten und Syntaxbeispiele finden Sie unter [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Da das `x:TypeArguments`\-Element eine Zeichenfolge annimmt und Typkonverterunterstützung aufweist, wird es in der Regel unter XAML als Attribut deklariert.  
  
 Im XAML\-Knotenstream können die von `x:TypeArguments` deklarierten Informationen von <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName> an einer `StartObject`\-Position im Knotenstream abgerufen werden.  Der Rückgabewert von <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName> ist eine Liste mit <xref:System.Xaml.XamlType>\-Werten.  Durch den Aufruf von <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=fullName> wird festgelegt, ob ein XAML\-Typ einen generischen Typ darstellen darf.  
  
## Regeln und Syntaxkonventionen für Generika in XAML  
 In XAML muss ein generischer Typ immer als eingeschränkt generisch dargestellt werden. Ein uneingeschränkt generischer Typ kann im XAML\-Typsystem oder einem XAML\-Knotenstream nicht vorhanden sein und kann nicht in XAML\-Markup dargestellt werden.  Auf einen generischen Typ kann in XAML\-Attributsyntax verwiesen werden, wenn von `x:TypeArguments` auf eine geschachtelte Typeinschränkung eines generischen Typs verwiesen wird oder wenn von `x:Type` ein CLR\-Typverweis für einen generischen Typ bereitgestellt wird.  Dies wird durch die von .NET Framework\-XAML\-Diensten definierte <xref:System.Xaml.Schema.XamlTypeTypeConverter>\-Klasse unterstützt.  
  
 Das von <xref:System.Xaml.Schema.XamlTypeTypeConverter> aktivierte XAML\-Attributsyntaxformular ändert die typische MSIL\/CLR\-Syntaxkonvention, in der spitze Klammern für Typen und Einschränkungen von Generika verwendet werden, und ersetzt stattdessen den Einschränkungscontainer durch Klammern.  Ein Beispiel finden Sie unter [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## Generika und XAML 2009\-Funktionen  
 Wenn Sie zum Abrufen von XAML\-Typen für gemeinsame Sprachprimitiven XAML 2009 verwenden, anstatt CLR\-Basistypen zuzuordnen, können Sie [integrierte XAML 2009\-Datentypen](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in `x:TypeArguments` verwenden.  Sie können z. B. Folgendes deklarieren \(Präfixzuordnungen werden nicht dargestellt, `x` ist jedoch der XAML\-Sprachnamespace in XAML 2009\):  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## Generikaunterstützung in WPF und anderen v3.5\-Frameworks  
 Zur Verwendung in XAML 2006 muss [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) auch für das gleiche Element wie `x:TypeArguments` angegeben werden, wenn WPF ausdrücklich als Ziel festgelegt ist, und das Element muss das Stammelement in einem XAML\-Dokument sein.  Das Stammelement muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden.  Ein Beispiel hierfür ist <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Mögliche Problemumgehungen zur Unterstützung generischer Verwendungen sind z. B. das Definieren einer benutzerdefinierten Markuperweiterung, die generische Typen zurückgeben kann, oder das Bereitstellen einer Umbruchklassendefinition, die von einem generischen Typ abgeleitet wird, aber die generische Einschränkung in einer eigenen Klassendefinition vereinfacht.  
  
 In WPF und mit [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] als Zielversion können Sie XAML 2009\-Funktionen mit `x:TypeArguments` verwenden, allerdings nur für Loose XAML \(nicht markupkompiliertes XAML\).  Markupkompilierte XAML für WPF und die BAML\-Form von XAML unterstützen die XAML 2009\-Schlüsselwörter und \-Funktionen derzeit nicht.  
  
 Benutzerdefinierte Workflows in [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] für [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] unterstützen keine generische XAML\-Verwendung.  
  
## Siehe auch  
 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)   
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)