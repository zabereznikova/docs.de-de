---
title: Reflektion in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET], reflection
- EventInfo class, reflection
- common language runtime, reflection
- FieldInfo class, reflection
- ParameterInfo class, reflection
- ConstructorInfo class, reflection
- Assembly class, reflection
- value types, reflection
- reflection, about reflection
- modules, reflection
- runtime, reflection
- Module class, reflection
- MethodInfo class, reflection
- PropertyInfo class, reflection
- type browsers
- reflection
- discovering type information at run time
- type system, reflection
ms.assetid: d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775
ms.openlocfilehash: 42944d8267d2e99fd9eb1a2cb28c0c81d3e9af75
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744569"
---
# <a name="reflection-in-net"></a>Reflektion in .NET

Mit den Klassen im <xref:System.Reflection>-Namespace sowie mit <xref:System.Type?displayProperty=nameWithType>können Sie Informationen [zu geladenen](../../standard/assembly/index.md) Assemblys und den darin definierten Typen abrufen, z. b [. Klassen](../../standard/base-types/common-type-system.md#classes), [Schnittstellen](../../standard/base-types/common-type-system.md#interfaces)und Werttypen (d. h. [Strukturen](../../standard/base-types/common-type-system.md#structures) und [Enumerationen](../../standard/base-types/common-type-system.md#enumerations)). Sie können auch mithilfe von Reflektion Typeninstanzen zur Laufzeit erstellen, diese aufrufen und darauf zugreifen. Themen zu bestimmten Aspekten der Reflektion finden Sie unter [Verwandte Themen](#related_topics) am Ende dieser Übersicht.
  
Das [Common Language Runtime](../../standard/clr.md)-Ladeprogramm verwaltet [Anwendungsdomänen](../app-domains/application-domains.md), bei denen es sich um definierte Begrenzungen um Objekte im gleichen Anwendungsbereich handelt. Diese Verwaltung umfasst das Laden jeder Assembly in die geeignete Anwendungsdomäne und das Steuern des Speicherlayouts der Typenhierarchie in jeder Assembly.  
  
[Assemblys](../app-domains/index.md) enthalten Module, Module enthalten Typen, und Typen enthalten Member. Mit der Reflektion werden Objekte bereitgestellt, die Assemblys, Module und Typen kapseln. Sie können mithilfe von Reflektion dynamisch eine Instanz eines Typen erzeugen, Typen an ein vorhandenes Objekt binden und Typinformationen eines vorhandenen Objekts abfragen. Sie können anschließend die Methoden des Typs aufrufen oder auf dessen Felder oder Eigenschaften zugreifen. Typische Verwendungen von Reflektionen umfassen die folgenden:  
  
- Verwenden Sie <xref:System.Reflection.Assembly>, um Assemblys zu definieren und zu laden, um Module zu laden, die im Assemblymanifest aufgeführt sind, und um einen Typ in seiner Assembly zu suchen und eine Instanz hiervon zu erstellen.  
  
- Verwenden Sie <xref:System.Reflection.Module>, um Informationen zu ermitteln, wie die Assembly, die das Modul enthält, und die Klassen im Modul. Sie können auch alle globalen Methoden oder andere spezifische, nicht globale Methoden abrufen, die im Modul definiert sind.  
  
- Verwenden Sie <xref:System.Reflection.ConstructorInfo>, um Informationen wie den Namen, die Parameter, die Zugriffsmodifizierer (wie `public` oder `private`) und Details zur Implementierung (wie `abstract` oder `virtual`) für einen Konstruktor abzurufen. Verwenden Sie die <xref:System.Type.GetConstructors%2A>- oder die <xref:System.Type.GetConstructor%2A>-Methode eines <xref:System.Type>, um einen bestimmten Konstruktor aufzurufen.  
  
- Verwenden Sie <xref:System.Reflection.MethodInfo>, um Informationen wie den Namen, den Rückgabetyp, die Parameter, die Zugriffsmodifizierer (wie `public` oder `private`) und Details zur Implementierung (wie `abstract` oder `virtual`) für eine Methode abzurufen. Verwenden Sie die <xref:System.Type.GetMethods%2A>- oder die <xref:System.Type.GetMethod%2A>-Methode eines <xref:System.Type>, um eine bestimmte Methode aufzurufen.  
  
- Verwenden Sie <xref:System.Reflection.FieldInfo>, um Informationen wie den Namen, die Zugriffsmodifizierer (wie `public` oder `private`) und Details zur Implementierung (wie `static`) für ein Feld abzurufen oder die Feldwerte abzurufen oder festzulegen.  
  
- Verwenden Sie <xref:System.Reflection.EventInfo>, um Informationen wie den Namen, den Datentyp das Ereignishandlers, benutzerdefinierte Attribute, den Deklarationstyp und den reflektierten Typ eines Ereignisses abzurufen und um Ereignishandler hinzuzufügen oder zu entfernen.  
  
- Verwenden Sie <xref:System.Reflection.PropertyInfo>, um Informationen wie den Namen, den Datentyp, den Deklarationstyp, den reflektierten Typ und die Status "Schreibgeschützt" oder "Beschreibbar" einer Eigenschaft abzurufen und um die Eigenschaftswert abzurufen oder festzulegen.  
  
- Verwenden Sie <xref:System.Reflection.ParameterInfo>, um Informationen wie den Namen eines Parameters, den Datentyp, ob es sich um einen Eingabe- oder Ausgabeparameter handelt und die Position des Parameters in der Methodensignatur abzurufen.  
  
- Verwenden Sie <xref:System.Reflection.CustomAttributeData>, um Informationen zu benutzerdefinierten Attributen abzurufen, wenn Sie im ausschließlich reflektionsbezogenen Kontext einer Anwendungsdomäne arbeiten. <xref:System.Reflection.CustomAttributeData> ermöglicht Ihnen, Attribute zu überprüfen, ohne Instanzen hiervon erstellen zu müssen.  
  
Die Klassen des <xref:System.Reflection.Emit>-Namespace stellen eine spezielle Form der Reflektion bereit, die es Ihnen ermöglicht, Typen zur Laufzeit zu erstellen.  
  
Reflektionen können auch zum Erstellen von Anwendungen verwendet werden, die als Typbrowser bezeichnet werden und es dem Benutzer ermöglichen, Typen auszuwählen und dann Informationen zu diesen Typen anzuzeigen.  
  
Dies ist eine weitere Verwendungsmöglichkeit von Reflektionen. Compiler für Sprachen wie JScript verwenden Reflektionen, um Symboltabellen zu erstellen. Die Klassen im <xref:System.Runtime.Serialization>-Namespace verwenden Reflektionen, um auf Daten zuzugreifen und um festzustellen, welche Felder beibehalten werden. Die Klassen im <xref:System.Runtime.Remoting>-Namespace verwenden Reflektionen indirekt über die Serialisierung.  
  
## <a name="runtime-types-in-reflection"></a>Laufzeittypen in Reflektion  
Reflektion stellt Klassen wie <xref:System.Type> und <xref:System.Reflection.MethodInfo> bereit, um Typen, Member, Parameter und andere Codeentitäten darzustellen. Wenn Sie jedoch Reflektion verwenden, arbeiten Sie nicht direkt mit diesen Klassen, von denen die meisten abstrakt sind (`MustInherit` in Visual Basic). Stattdessen arbeiten Sie mit Typen, die von der CLR (Common Language Runtime) bereitgestellt werden.  
  
Wenn Sie beispielsweise den C#-Operator `typeof` (`GetType` in Visual Basic) verwenden, um ein <xref:System.Type>-Objekt abzurufen, handelt es sich in Wirklichkeit um ein `RuntimeType`-Objekt. `RuntimeType` ist von <xref:System.Type> abgeleitet und stellt Implementierungen aller abstrakten Methoden bereit.  
  
Diese Laufzeitklassen sind `internal` (`Friend` in Visual Basic). Sie werden nicht getrennt von den Basisklassen dokumentiert, da ihr Verhalten in der Dokumentation der Basisklasse beschrieben wird.  
  
<a name="related_topics"></a>   

## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|BESCHREIBUNG|  
|-----------|-----------------|  
|[Anzeigen von Typinformationen](viewing-type-information.md)|Beschreibt die <xref:System.Type>-Klasse und stellt Codebeispiele bereit, die zeigen, wie <xref:System.Type> mit verschiedenen Reflektionsklassen verwendet wird, um Informationen zu Konstruktoren, Methoden, Feldern, Eigenschaften und Ereignissen abzurufen.|  
|[Reflektion und generische Typen](reflection-and-generic-types.md)|Erläutert, wie die Reflektion die Typparameter und die Typargumente von generischen Typen und generischen Methoden behandelt.|  
|[Security Considerations for Reflection (Sicherheitsüberlegungen für die Reflektion)](security-considerations-for-reflection.md)|Beschreibt die Regeln, die festlegen, bis zu welchem Grad Reflektion verwendet werden kann, um Typinformationen abzurufen und auf Typen zuzugreifen.|  
|[Dynamically Loading and Using Types (Dynamisches Laden und Verwenden von Typen)](dynamically-loading-and-using-types.md)|Beschreibt die benutzerdefinierte Bindungsschnittstelle der Reflektion, die spätes Binden unterstützt.|  
|[Gewusst wie: Laden von Assemblys in den reflexionsbezogenen Kontext](how-to-load-assemblies-into-the-reflection-only-context.md)|Beschreibt den reflektionsbezogenen Ladungskontext. Zeigt, wie eine Assembly geladen wird, wie der Kontext getestet und wie die Attribute überprüft werden, die im reflektionsbezogenen Kontext auf eine Assembly angewendet wurden.|  
|[Zugreifen auf benutzerdefinierte Attribute](accessing-custom-attributes.md)|Zeigt, wie mithilfe der Reflektion das Vorhandensein von Attributen und Werten abgefragt werden kann.|  
|[Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)](specifying-fully-qualified-type-names.md)|Beschreibt das Format von vollqualifizierten Typnamen mit den Begriffen von BNF (Backus-Naur Form) sowie die Syntax, die erforderlich ist, um Sonderzeichen, Assemblynamen, Zeiger, Verweise und Arrays anzugeben.|  
|[ How to: Hook Up a Delegate Using Reflection (Vorgehensweise: Verknüpfen mit einem Delegaten mit Reflektion)](how-to-hook-up-a-delegate-using-reflection.md)|Erläutert, wie ein Delegat für eine Methode erstellt und dieser Delegat mit einem Ereignis verknüpft wird. Beschreibt, wie eine Ereignisbehandlungsmethode zur Laufzeit mit <xref:System.Reflection.Emit.DynamicMethod> erstellt wird.|  
|[Ausgeben von dynamischen Methoden und Assemblys](emitting-dynamic-methods-and-assemblies.md)|Erläutert, wie dynamische Assemblys und dynamische Methoden generiert werden.|  
  
## <a name="reference"></a>Verweis  

<xref:System.Type?displayProperty=nameWithType>  
  
<xref:System.Reflection>  
  
<xref:System.Reflection.Emit>  
