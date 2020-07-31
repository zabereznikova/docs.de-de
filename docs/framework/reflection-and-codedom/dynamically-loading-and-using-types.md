---
title: Dynamisches Laden und Verwenden von Typen
description: Hier erfahren Sie mehr über das dynamische Laden und Verwenden von Typen in .NET. Verwenden Sie die Reflexion, mit der die Infrastruktur bereitgestellt wird, die von Sprachcompilern für die Implementierung impliziter später Bindungen verwendet wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- late binding, about late binding
- early binding
- dynamically loading and using types
- implicit late binding
- reflection, dynamically using types
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
ms.openlocfilehash: 39a4a9a2ff77cb900db7f39a55dc17a5b8c62cf3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475085"
---
# <a name="dynamically-loading-and-using-types"></a>Dynamisches Laden und Verwenden von Typen
Reflektion stellt Infrastruktur bereit, die von Sprachcompilern für die Implementierung impliziter später Bindungen verwendet wird. Unter Binden versteht man das Auffinden der Deklaration (d.h. der Implementierung), die einem eindeutig festgelegten Typ entspricht. Wenn dieser Prozess zur Runtime und nicht zum Zeitpunkt der Kompilierung stattfindet, wird von einer späten Bindung gesprochen. Visual Basic ermöglicht Ihnen, die implizite späte Bindung in Ihrem Code zu verwenden. Der Visual Basic-Compiler ruft eine Hilfsmethode auf, die mithilfe von Reflektion den Objekttyp abruft. Aufgrund der an die Hilfsmethode übergebenen Argumente wird die entsprechende Methode zur Runtime aufgerufen. Diese Argumente sind die Instanz (ein Objekt), auf der die Methode aufgerufen werden muss, der Namen der aufgerufenen Methode (eine Zeichenfolge) und die Argumente, die an die aufgerufene Methode übergeben werden (ein Array von Objekten).  
  
 Im folgenden Beispiel verwendet der Visual Basic-Compiler Reflektion implizit, um eine Methode für ein Objekt aufzurufen, dessen Typ zur Kompilierzeit nicht bekannt ist. Ein **HelloWorld**-Klasse verfügt über eine **PrintHello**-Methode, die „Hello World“ zusammen mit anderem Text ausgibt, der an die **PrintHello**-Methode übergeben wurde. Die in diesem Beispiel aufgerufene **PrintHello**-Methode ist eigentlich eine <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>-Methode. Im Visual Basic-Code kann die **PrintHello**-Methode aufgerufen werden, als ob der Typ des Objekts (helloObj) schon zur Kompilierzeit bekannt wäre (frühe Bindung) statt erst zur Runtime (späte Bindung).  
  
```vb
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
  
## <a name="custom-binding"></a>Benutzerdefinierte Bindung  
 Abgesehen davon, dass Reflektion implizit von Compilern für das späte Binden verwendet wird, kann sie auch explizit im Code für das späte Binden angewandt werden.  
  
 Die [Common Language Runtime](../../standard/clr.md) unterstützt verschiedene Programmiersprachen, wobei sich die Bindungsregeln dieser Sprachen unterscheiden. Beim frühen Binden können Codegeneratoren den Bindungsvorgang vollständig steuern. Beim späten Binden durch Reflektion muss der Vorgang durch eine benutzerdefinierte Bindung gesteuert werden. Die <xref:System.Reflection.Binder>-Klasse stellt die benutzerdefinierte Steuerung der Auswahl und des Aufrufs von Membern bereit.  
  
 Mithilfe der benutzerdefinierten Bindung können Sie eine Assembly zur Runtime laden, Informationen über Typen in dieser Assembly abrufen, den gewünschten Typ angeben und dann für diesen Typ die Methoden aufrufen oder auf die Felder bzw. Eigenschaften zugreifen. Diese Technik ist hilfreich, wenn Sie den Typ eines Objekts zur Kompilierzeit nicht kennen, z.B., wenn der Objekttyp von der Benutzereingabe abhängt.  
  
 Das folgende Beispiel zeigt einen einfachen benutzerdefinierten Binder, der keine Argumenttypumwandlung bereitstellt. Der Code für `Simple_Type.dll` steht vor dem Hauptbeispiel. Achten Sie darauf, dass Sie `Simple_Type.dll` erstellen und dann zur Buildzeit einen Verweis darauf in das Projekt einbinden.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### <a name="invokemember-and-createinstance"></a>InvokeMember und CreateInstance  
 Verwenden Sie <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>, um einen Member eines Typs aufzurufen. Die **CreateInstance**-Methoden verschiedener Klassen wie <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.CreateInstance%2A?displayProperty=nameWithType> sind spezielle Formen von **InvokeMember**, die neue Instanzen des angegebenen Typs erstellen. Die **Binder**-Klasse wird in diesen Methoden für die Auflösung von Überladungen und die Koersion von Argumenten verwendet.  
  
 Im folgenden Beispiel werden drei mögliche Kombinationen der Argumentkoersion (Typkonvertierung) und Memberauswahl dargestellt. Im 1. Fall ist keine Argumentkoersion oder Memberauswahl erforderlich. Im 2. Fall ist nur die Memberauswahl notwendig. Im 3. Fall muss nur die Argumentkoersion vorgenommen werden.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 Die Überladungsauflösung ist nötig, wenn mehr als ein Member mit demselben Namen verfügbar ist. Die Methoden <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=nameWithType> und <xref:System.Reflection.Binder.BindToField%2A?displayProperty=nameWithType> werden zum Auflösen der Bindung zu einem einzelnes Member verwendet. **Binder.BindToMethod** stellt außerdem die Auflösung von Eigenschaften über die Eigenschaftenaccessoren **get** und **set** bereit.  
  
 **BindToMethod** gibt die aufzurufende <xref:System.Reflection.MethodBase>-Klasse oder einen NULL-Verweis zurück (**Nothing** in Visual Basic), wenn kein solcher Aufruf möglich ist. Die Rückgabewert von **MethodBase** muss keiner der im *match*-Parameter enthaltenen sein, obwohl dies normalerweise der Fall ist.  
  
 Wenn ByRef-Argumente vorhanden sind, kann der Aufrufer sie bei Bedarf wiederherstellen. Aus diesem Grund ermöglicht es **Binder** einem Client, das Argumentarray wieder in seine ursprüngliche Form zu versetzen, wenn es von **BindToMethod** bearbeitet wurde. Dazu muss dem Aufrufer gewährleistet werden, dass die Reihenfolge der Argumente nicht verändert wurde. Wenn Argumente nach Namen übergeben werden, sortiert **Binder** das Argumentarray neu, und dies wird dem Aufrufer angezeigt. Weitere Informationen finden Sie unter <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=nameWithType>.  
  
 Die Menge der verfügbaren Member sind diejenigen, die im Typ oder einem Basistyp definiert. Wenn <xref:System.Reflection.BindingFlags> angegeben wird, werden Member aller Zugriffsebenen in den Satz zurückgegeben. Wenn **BindingFlags.NonPublic** nicht angegeben wird, muss der Binder die Zugriffsregeln erzwingen. Wenn die Bindungsflags **Public** oder **NonPublic** angegeben werden, müssen Sie auch die Bindungsflags **Instance** oder **Static** angeben. Andernfalls werden keine Member zurückgegeben.  
  
 Wenn nur ein Member mit dem angegebenen Namen verfügbar ist, ist kein Rückruf notwendig, und die Bindung wird auf der Methode ausgeführt. Fall 1 des Codebeispiels veranschaulicht dies: Hier ist nur eine **PrintBob**-Methode verfügbar, und daher ist kein Rückruf erforderlich.  
  
 Wenn sich mehr als ein Member im verfügbaren Satz befindet, werden alle diese Methoden an **BindToMethod** übergeben, das die richtige Methode ausgewählt und sie zurückgibt. Bei Fall 2 des Codebeispiels gibt es zwei Methoden namens **PrintValue**. Die geeignete Methode wird über einen Aufruf von **BindToMethod** ausgewählt.  
  
 <xref:System.Reflection.Binder.ChangeType%2A> führt die Argumentkoersion (Typkonvertierung) aus, die die eigentlichen Argumente in den Typ der formalen Argumente der ausgewählten Methode konvertiert. **ChangeType** wird für jedes Argument aufgerufen, selbst wenn die Typen exakt übereinstimmen.  
  
 In Fall 3 des Codebeispiels wird ein Argument des Typs **String** mit dem Wert „5,5“ an eine Methode mit einem formalen Argument vom Typ **Double** übergeben. Damit der Aufruf erfolgreich ausgeführt werden kann, muss der Zeichenfolgenwert „5,5“ in einen Double-Wert konvertiert werden. Für diese Konvertierung ist **ChangeType** zuständig.  
  
 **ChangeType** führt nur verlustfreie oder [Erweiterungsumwandlungen](../../standard/base-types/type-conversion.md) aus, wie in der folgenden Tabelle dargestellt.  
  
|Quelltyp|Zieltyp|  
|-----------------|-----------------|  
|Beliebiger Typ|Dessen Basistyp|  
|Beliebiger Typ|Die implementierte Schnittstelle|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|Nichtverweistyp|Verweistyp|  
  
 Die <xref:System.Type>-Klasse verfügt über **Get**-Methoden, die Parameter des Typs **Binder** nutzen, um Verweise auf einen bestimmten Member aufzulösen. <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType>, <xref:System.Type.GetMethod%2A?displayProperty=nameWithType>, und <xref:System.Type.GetProperty%2A?displayProperty=nameWithType> suchen nach einem bestimmten Member des aktuellen Typs, indem sie die Signaturinformationen für diesen Member zur Verfügung stellen. <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=nameWithType> und <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=nameWithType> werden wieder aufgerufen, um die jeweiligen Signaturinformationen der geeigneten Methoden auszuwählen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- [Anzeigen von Typinformationen](viewing-type-information.md)
- [Typkonvertierung in .NET Framework](../../standard/base-types/type-conversion.md)
