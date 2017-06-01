---
title: "Angeben vollst&#228;ndig gekennzeichneter Typnamen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Namen"
  - "Backus-Naur-Form"
  - "BNF"
  - "Vollqualifizierte Typnamen"
  - "IDENTIFIER"
  - "Sprachen, BNF-Grammatik"
  - "Namen [.NET Framework], Assemblys"
  - "Namen [.NET Framework], Vollqualifizierte Typnamen"
  - "Reflektion, Vollqualifizierte Typnamen"
  - "Sonderzeichen"
  - "Token"
  - "Typnamen"
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Angeben vollst&#228;ndig gekennzeichneter Typnamen
Gültige Eingaben für eine Reihe von Reflektionsoperationen erfordern die spezifische Angabe von Typnamen.  Ein vollständig qualifizierter Typname besteht aus der Angabe eines Assemblynamens, der Festlegung eines Namespaces und einem Typnamen.  Angaben von Typnamen werden von Methoden wie <xref:System.Type.GetType%2A?displayProperty=fullName>, <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName> und <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> verwendet.  
  
## Die Grammatik der Backus\-Naur\-Form für Typnamen  
 Die Backus\-Naur\-Form \(BNF\) definiert die Syntax formaler Sprachen.  Die folgende Tabelle gibt führt die lexikalischen BNF\-Regeln auf, durch die das Erkennen einer gültigen Eingabe beschrieben wird.  Terminale \(nicht weiter reduzierbare Sprachelemente\) werden in Großbuchstaben dargestellt.  Nicht\-Terminale \(weiter reduzierbare Elemente\) werden in gemischter Groß\-\/Kleinschreibung oder als Zeichenfolgen dargestellt, die in einfache Anführungszeichen eingeschlossen sind \(die einfachen Anführungszeichen gehören nicht zur Syntax\).  Das Pipezeichen \(&#124;\) kennzeichnet Regeln, die über untergeordnete Regeln verfügen.  
  
|BNF\-Grammatik für vollständig qualifizierte Typnamen|  
|-----------------------------------------------------------|  
|TypeSpec                          :\=   ReferenceTypeSpec<br /><br /> &#124;     SimpleTypeSpec|  
|ReferenceTypeSpec: \= SimpleTypeSpec '&'|  
|SimpleTypeSpec                :\=   PointerTypeSpec<br /><br /> &#124;     ArrayTypeSpec<br /><br /> &#124;     TypeName|  
|PointerTypeSpec                :\=   SimpleTypeSpec '\*'|  
|ArrayTypeSpec                  :\=   SimpleTypeSpec '\[ReflectionDimension\]'<br /><br /> &#124;     SimpleTypeSpec '\[ReflectionEmitDimension\]'|  
|ReflectionDimension           :\=   '\*'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|ReflectionEmitDimension    :\=   '\*'<br /><br /> &#124;     Number '..' Zahl<br /><br /> &#124;     Number '...'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|Number                            :\=   \[0\-9\]\+|  
|TypeName                         :\=   NamespaceTypeName<br /><br /> &#124;     NamespaceTypeName ',' AssemblyNameSpec|  
|NamespaceTypeName        :\=   NestedTypeName<br /><br /> &#124;     NamespaceSpec '.' NestedTypeName|  
|NestedTypeName               :\=   IDENTIFIER<br /><br /> &#124;     NestedTypeName '\+' IDENTIFIER|  
|NamespaceSpec                 :\=   IDENTIFIER<br /><br /> &#124;     NamespaceSpec '.' IDENTIFIER|  
|AssemblyNameSpec           :\=   IDENTIFIER<br /><br /> &#124;     IDENTIFIER ',' AssemblyProperties|  
|AssemblyProperties            :\=   AssemblyProperty<br /><br /> &#124;     AssemblyProperties ',' AssemblyProperty|  
|AssemblyProperty              :\=   AssemblyPropertyName '\=' AssemblyPropertyValue|  
  
## Angeben von Sonderzeichen  
 In einem Typennamen ist ein IDENTIFIER jeder von den Regeln einer Sprache als gültig erkannter Name.  
  
 Der umgekehrte Schrägstrich dient als Escapezeichen, um folgende Tokens zu trennen, wenn diese innerhalb eines IDENTIFIER verwendet werden.  
  
|Token|Bedeutung|  
|-----------|---------------|  
|\\,|Assemblytrennzeichen.|  
|\\\+|Trennzeichen für geschachtelte Typen.|  
|\\&|Referenztyp.|  
|\\\*|Zeigertyp.|  
|\\\[|Begrenzungszeichen eines Arrays.|  
|\\\]|Begrenzungszeichen eines Arrays.|  
|\\.|Der umgekehrte Schrägstrich vor einem Punkt wird nur verwendet, wenn der Punkt innerhalb einer Arraybezeichnung auftritt.  Punkte in **NamespaceSpec** erhalten keinen umgekehrten Schrägstrich.|  
|\\\\|Umgekehrter Schrägstrich als Literal.|  
  
 Beachten Sie, dass Leerräume in allen **TypeSpec**\-Komponenten mit Ausnahme von **AssemblyNameSpec** relevant sind.  Leerräume in **AssemblyNameSpec** sind nur vor dem Trennzeichen "," relevant, dahinter werden sie ignoriert.  
  
 Reflektionsklassen, z. B. <xref:System.Type.FullName%2A?displayProperty=fullName>, geben den zerlegten Namen zurück, sodass dieser in Aufrufen von <xref:System.Type.GetType%2A> verwendet werden kann, wie in `MyType.GetType(myType.FullName)`.  
  
 Ein Beispiel für einen vollständig qualifizierten Typnamen ist `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.  
  
 Wäre der Namespace `Ozzy.Out+Back`, müsste dem Pluszeichen ein umgekehrter Schrägstrich vorangestellt werden.  Andernfalls würde es vom Parser als Schachtelungstrennzeichen interpretiert werden.  Durch Reflektion wird diese Zeichenfolge zu `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.  
  
## Festlegen von Assemblynamen  
 Zur Festlegung eines Assemblynamens ist als Mindestangabe der wörtliche Name \(IDENTIFIER\) der Assembly erforderlich.  Dem IDENTIFIER kann eine durch Trennzeichen getrennte Auflistung von Eigenschaft\/Wert\-Paaren angefügt werden, wie in der folgenden Tabelle beschrieben:  Namen für IDENTIFIER sollten nach denselben Regeln wie Dateinamen vergeben werden.  Bei einem IDENTIFIER wird zwischen Groß\-\/Kleinschreibung unterschieden.  
  
|Name der Eigenschaft|**Beschreibung**|Gültige Werte|  
|--------------------------|----------------------|-------------------|  
|**Version**|Versionsnummer der Assembly|*Major.Minor.Build.Revision*, \(*Major*, *Minor*, *Build* und *Revision* sind ganze Zahlen von 0 bis einschließlich 65535\).|  
|**PublicKey**|Vollständiger öffentlicher Schlüssel|Zeichenfolgenwert eines vollständigen öffentlichen Schlüssels im Hexadezimalformat.  Geben Sie einen NULL\-Verweis \(**Nothing** in Visual Basic\) an, um eine Assembly explizit als privat zu kennzeichnen.|  
|**PublicKeyToken**|Token eines öffentlichen Schlüssels \(8\-Byte\-Hash des vollständigen öffentlichen Schlüssels\)|Zeichenfolgenwert eines öffentlichen Schlüsseltokens im Hexadezimalformat.  Geben Sie einen NULL\-Verweis \(**Nothing** in Visual Basic\) an, um eine Assembly explizit als privat zu kennzeichnen.|  
|**Kultur**|Kultur der Assembly|Kultur der Assembly im RFC\-1766\-Format bzw. "neutral" für sprachenunabhängige Assemblys \(d. h. keine Satellitenassemblys\).|  
|**Benutzerdefiniert**|Benutzerdefiniertes Binary Large Object \(BLOB\).  Derzeit wird dies nur von Assemblys verwendet, die mit dem [Native Image Generator\-Tool \(NGEN\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) generiert wurden.|Benutzerdefinierte Zeichenfolge, die vom Native Image Generator\-Tool \(NGEN\) verwendet wird, um den Assemblycache zu benachrichtigen, dass die Assembly ein systemeigenes Bild und somit im systemeigenen Cache zu installieren ist.  Wird auch Zap\-Zeichenfolge genannt.|  
  
 Im folgenden Beispiel wird ein **AssemblyName** für eine einfach benannte Assembly mit Standardkultur angegeben.  
  
```csharp  
com.microsoft.crypto, Culture=""   
```  
  
 Im folgenden Beispiel wird ein vollständiger Verweis auf eine Assembly mit starkem Namen und der Kultur "en" gegeben.  
  
```csharp  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0   
```  
  
 In den folgenden Beispielen wird jeweils ein teilweise spezifizierter **AssemblyName** angegeben, dem entweder eine Assembly mit einfachem oder mit starkem Namen entspricht.  
  
```csharp  
com.microsoft.crypto  
com.microsoft.crypto, Culture=""  
com.microsoft.crypto, Culture=en   
```  
  
 In den folgenden Beispielen wird jeweils ein teilweise spezifizierter **AssemblyName** angegeben, dem nur eine Assembly mit einfachem Namen entspricht.  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=null   
com.microsoft.crypto, Culture=en, PublicKeyToken=null  
```  
  
 In den folgenden Beispielen wird jeweils ein teilweise spezifizierter **AssemblyName** angegeben, dem nur eine Assembly mit starkem Namen entspricht.  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0  
```  
  
## Angeben von Zeigern  
 SimpleTypeSpec\* stellt einen nicht verwalteten Zeiger dar.  Ein Beispiel: Um einen Zeiger auf den Typ **MyType** zu definieren, verwenden Sie `Type.GetType("MyType*")`.  Um einen Zeiger auf diesen Zeiger \(d. h. den Zeiger auf den Typ **MyType**\) zu definieren, verwenden Sie `Type.GetType("MyType**")`.  
  
## Angeben von Verweisen  
 SimpleTypeSpec & stellt einen verwalteten Zeiger oder einen Verweis dar.  Ein Beispiel: Um einen Verweis auf den Typ **MyType** zu definieren, verwenden Sie `Type.GetType("MyType &")`.  Im Gegensatz zu Zeigern sind Verweise auf eine Ebene beschränkt.  
  
## Angeben von Arrays  
 Gemäß der BNF\-Grammatik wird ReflectionEmitDimension nur auf unvollständige Typdefinitionen angewendet, die über <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName> abgerufen werden.  Unvollständige Typdefinitionen sind <xref:System.Reflection.Emit.TypeBuilder>\-Objekte, die mit [Reflection.Emit](frlrfSystemReflectionEmit) erstellt wurden, für die <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=fullName> aber nicht aufgerufen wurde.  Mit **ReflectionDimension** kann jede Typdefinition abgerufen werden, die vervollständigt wurde, d. h. ein Typ, der geladen wurde.  
  
 Bei der Reflektion wird auf Arrays zugegriffen, indem der Rang des Arrays angegeben wird:  
  
-   `Type.GetType("MyArray[]")` definiert ein eindimensionales Array mit der Untergrenze 0.  
  
-   `Type.GetType("MyArray[*]")` definiert ein eindimensionales Array mit unbekannter Untergrenze.  
  
-   `Type.GetType("MyArray[][]")` definiert das Array eines zweidimensionalen Arrays.  
  
-   `Type.GetType("MyArray[*,*]")` definiert ein rechteckiges, zweidimensionales Array mit unbekannten Untergrenzen.  
  
 Beachten Sie, dass aus Sicht der Common Language Runtime `MyArray[] != MyArray[*]` gilt. Für mehrdimensionale Arrays sind beide Notationen äquivalent.  Dies bedeutet, dass der Ausdruck `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` als **true** bewertet wird.  
  
 **ModuleBuilder.GetType** interpretiert `MyArray[0..5]` als eindimensionales Array der Länge 6 mit der Untergrenze 0 und  `MyArray[4…]` als eindimensionales Array unbekannter Größe mit der Untergrenze 4.  
  
## Siehe auch  
 <xref:System.Reflection.AssemblyName>   
 <xref:System.Reflection.Emit.ModuleBuilder>   
 <xref:System.Reflection.Emit.TypeBuilder>   
 <xref:System.Type.FullName%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>   
 [Anzeigen von Typinformationen](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)