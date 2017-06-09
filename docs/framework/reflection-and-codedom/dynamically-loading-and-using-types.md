---
title: "Dynamisches Laden und Verwenden von Typen | Microsoft Docs"
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
  - "Dynamisches Laden und Verwenden von Typen"
  - "Frühes Binden"
  - "Implizites spätes Binden"
  - "Späte Bindung, Informationen über spätes Binden"
  - "Reflektion, Dynamisches Verwenden von Typen"
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Dynamisches Laden und Verwenden von Typen
Reflektion stellt die Infrastruktur zur Verfügung, die Sprachcompiler wie [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] oder JScript verwenden, um implizite späte Bindung zu implementieren.  Bindung besteht im Auffinden der Deklaration \(d. h. der Implementierung\), die sich auf einen eindeutig festgelegten Typ bezieht.  Wenn dieser Prozess nicht während der Kompilierungszeit, sondern während der Laufzeit stattfindet, wird er als späte Bindung bezeichnet.  [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] lässt die Verwendung der impliziten späten Bindung im Code zu. Der Visual Basic\-Compiler ruft eine Hilfsmethode auf, die unter Verwendung von Reflektion den Objekttyp abruft.  Die an die Hilfsmethode übergebenen Argumente sorgen dafür, dass die richtige Methode zur Laufzeit aufgerufen wird.  Es handelt sich um folgende Argumente: die Instanz \(ein Objekt\), für das die Methode aufgerufen werden soll, der Name der aufgerufenen Methode \(eine Zeichenfolge\) sowie die Argumente, die der aufgerufenen Methode übergeben werden \(ein Objektarray\).  
  
 Im folgenden Beispiel verwendet der Visual Basic\-Compiler Reflektion, um implizit eine Methode für ein Objekt aufzurufen, dessen Typ zum Zeitpunkt der Kompilierung nicht bekannt ist.  Eine **HelloWorld**\-Klasse enthält eine **PrintHello**\-Methode, die "Hello World" zusammen mit anderem, an sie übergebenen Text ausgibt.  Die in diesem Beispiel aufgerufene **PrintHello**\-Methode ist eigentlich ein <xref:System.Type.InvokeMember%2A?displayProperty=fullName>; im Visual Basic\-Code kann die **PrintHello**\-Methode so aufgerufen werden, als wäre der Objekttyp bereits zur Kompilierungszeit \(frühes Binden\) und nicht erst zur Laufzeit \(spätes Binden\) bekannt.  
  
```  
Imports System  
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## Benutzerdefiniertes Binden  
 Reflektion kann nicht nur von Compilern implizit für spätes Binden eingesetzt werden, sondern auch explizit im Code.  
  
 [Common Language Runtime](../../../docs/standard/clr.md) unterstützt mehrere Programmiersprachen; die Bindungsregeln dieser Sprachen unterscheiden sich voneinander.  Im Fall früher Bindung können Code\-Generatoren den Bindungsvorgang vollständig kontrollieren.  Im Fall später Bindung durch Reflektion muss der Vorgang durch benutzerdefinierte Bindung gesteuert werden.  Die <xref:System.Reflection.Binder>\-Klasse ermöglicht die benutzerdefinierte Steuerung für die Auswahl und den Aufruf von Membern.  
  
 Mit benutzerdefinierter Bindung können Sie eine Assembly zur Laufzeit laden, Informationen über Typen in dieser Assembly erhalten, den gewünschten Typ festlegen und anschließend für diesen Typ Methoden aufrufen oder auf Felder und Eigenschaften zugreifen.  Diese Technik ist besonders nützlich, wenn ein Objekttyp zur Kompilierungszeit nicht bekannt ist, z. B. weil der Typ von Benutzereingaben abhängt.  
  
 Das folgende Beispiel veranschaulicht einen einfachen benutzerdefinierten Binder, der keine Argumenttypkonvertierung durchführt.  Dem Hauptbeispiel geht Code für `Simple_Type.dll` voran.  Stellen Sie sicher, dass Sie `Simple_Type.dll` erstellen und dann in das Projekt zur Erstellungszeit einen Verweis darauf aufnehmen.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### InvokeMember und CreateInstance  
 Verwenden Sie <xref:System.Type.InvokeMember%2A?displayProperty=fullName>, um einen Member eines Typs aufzurufen.  Die **CreateInstance**\-Methoden verschiedener Klassen, z. B. [System.Activator](frlrfSystemActivatorClassCreateInstanceTopic) und [System.Reflection.Assembly](frlrfSystemReflectionAssemblyClassCreateInstanceTopic), sind spezielle Formen von **InvokeMember**, die neue Instanzen des angegebenen Typs erzeugen.  Die **Binder**\-Klasse wird für Überladungsauflösung und Argument\-Coertion in diesen Methoden verwendet.  
  
 Im folgenden Beispiel werden die drei möglichen Kombinationen von Argument\-Coertion \(Typkonvertierung\) und Memberauswahl dargestellt.  Fall 1: Argument\-Coertion oder Memberauswahl wird nicht benötigt.  Fall 2: Nur Memberauswahl wird benötigt.  Fall 3: Nur Argument\-Coertion wird benötigt.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 Überladungsauflösung wird dann benötigt, wenn mehrere Member gleichen Namens zur Verfügung stehen.  Die <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=fullName>\-Methode und die <xref:System.Reflection.Binder.BindToField%2A?displayProperty=fullName>\-Methode werden verwendet, um Bindungen an einen einzelnen Member aufzulösen.  Mit **Binder.BindToMethod** können Eigenschaften durch die Eigenschaften\-Accessoren **get** und **set** aufgelöst werden.  
  
 **BindToMethod** gibt den aufzurufenden <xref:System.Reflection.MethodBase> zurück. Ist ein solcher Aufruf nicht möglich, wird ein NULL\-Verweis \(in Visual Basic **Nothing**\) zurückgegeben.  Der Rückgabewert von **MethodBase** ist nicht unbedingt im *match*\-Parameter enthalten, obwohl dies der Normalfall ist.  
  
 Sind ByRef\-Argumente vorhanden, könnte der Aufrufer die Argumente zurückverlangen.  Aus diesem Grund erlaubt **Binder** einem Client, das Argumentarray seinem ursprünglichen Zustand zuzuordnen, falls das Array durch **BindToMethod** verändert wurde.  Zu diesem Zweck muss dem Aufrufer gewährleistet werden, dass die Reihenfolge der Argumente unverändert bleibt.  Wenn Argumente nach Namen übergeben werden, erstellt **Binder** eine neue Anordnung des Argumentarrays.  Nur dieses ist für den Aufrufer sichtbar.  Weitere Informationen finden Sie unter <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=fullName>.  
  
 Die Menge verfügbarer Member besteht aus den im Typ oder einem beliebigen Basistyp definierten Membern.  Ist [BindingFlags.NonPublic](frlrfSystemReflectionBindingFlagsClassTopic) angegeben, werden Member unabhängig von ihrer Zugänglichkeit an die Menge zurückgegeben.  Andernfalls muss der Binder Zugänglichkeitsregeln erzwingen.  Wenn die Bindungsflags **Public** oder **NonPublic** gesetzt sind, müssen auch die Bindungsflags **Instance** oder **Static** gesetzt werden, sonst wird kein Member zurückgegeben.  
  
 Gibt es nur einen Member des jeweiligen Namens, ist kein Rückruf erforderlich, und die Bindung wird für diese Methode vorgenommen.  Im 1. Fall des Codebeispiels gibt es nur eine verfügbare **PrintBob**\-Methode, daher ist kein Rückruf erforderlich.  
  
 Gibt es mehrere Member in der verfügbaren Menge, werden alle diese Methoden an **BindToMethod** übergeben, wodurch die richtige Methode ausgewählt und zurückgegeben wird.  Im 2. Fall des Codebeispiels gibt es zwei Methoden namens **PrintValue**.  Die richtige Methode wird durch einen Aufruf von **BindToMethod** ausgewählt.  
  
 <xref:System.Reflection.Binder.ChangeType%2A> führt Argument\-Coertion \(Typkonvertierung\) durch, wobei die tatsächlichen Argumente in den Typ der formalen Argumente der ausgewählten Methode konvertiert werden.  **ChangeType** wird für jedes Argument aufgerufen, selbst dann, wenn die Typen exakt übereinstimmen.  
  
 Im 3. Fall des Codebeispiels wird ein Argument des Typs **String** mit dem Wert "5,5" an eine Methode mit einem formalen Argument vom Typ **Double** übergeben.  Für einen erfolgreichen Aufruf muss der Zeichenfolgenwert "5,5" in einen Double\-Wert konvertiert werden.  Die Konvertierung wird von **ChangeType** übernommen.  
  
 **ChangeType** führt nur verlustfreie oder [erweiternde Coertionen](../../../docs/standard/base-types/type-conversion.md) aus, wie in folgender Tabelle beschrieben:  
  
|Quelltyp|Zieltyp|  
|--------------|-------------|  
|Beliebiger Typ|Der entsprechende Basistyp.|  
|Beliebiger Typ|Implementierte Schnittstelle|  
|Char|UInt16, UInt32, Int32, Uint64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|Kein Referenztyp|Verweistyp|  
  
 Die <xref:System.Type>\-Klasse enthält **Get**\-Methoden, die mithilfe von Parametern vom Typ **Binder** Verweise auf einen bestimmten Member auflösen.  <xref:System.Type.GetConstructor%2A?displayProperty=fullName>, <xref:System.Type.GetMethod%2A?displayProperty=fullName> und <xref:System.Type.GetProperty%2A?displayProperty=fullName> suchen nach einem bestimmten Member des aktuellen Typs, indem sie die Signaturinformationen für diesen Member zur Verfügung stellen.  <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=fullName> und <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=fullName> werden zur Auswahl der jeweiligen Signaturinformationen der entsprechenden Methoden aufgerufen.  
  
## Siehe auch  
 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 [Anzeigen von Typinformationen](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Typkonvertierung in .NET Framework](../../../docs/standard/base-types/type-conversion.md)