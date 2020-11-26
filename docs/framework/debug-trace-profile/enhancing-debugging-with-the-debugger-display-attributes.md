---
title: Verbessern des Debuggens mit den Debuggeranzeigeattributen
description: Beginnen Sie mit den Debugger-Anzeige Attributen in .net, die es dem typentwickler ermöglichen, auch anzugeben, wie der Typ aussehen soll, wenn er in einem Debugger angezeigt wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: 2e556358490409a0fa7b345c4454eb43cf607e32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244365"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a>Verbessern des Debuggens mit den Debuggeranzeigeattributen

Debuggeranzeigeattribute ermöglichen es dem Entwickler des Typs, der dessen Laufzeitverhalten angibt und am besten versteht, ebenfalls anzugeben, wie der Typ aussieht, wenn er in einem Debugger angezeigt wird. Zusätzlich können Debuggeranzeigeattribute, die eine `Target`-Eigenschaft bereitstellen, von den Benutzern auf Assemblyebene angewendet werden, ohne dass diese den Quellcode kennen müssen. Das <xref:System.Diagnostics.DebuggerDisplayAttribute>-Attribut steuert die Anzeige eines Typs oder Members in den Variablenfenstern des Debuggers. Das <xref:System.Diagnostics.DebuggerBrowsableAttribute>-Attribut bestimmt, ob und wie ein Feld oder eine Eigenschaft in den Variablenfenstern des Debuggers angezeigt wird. Das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>-Attribut gibt einen Ersatztyp oder einen Proxy für einen Typ an und ändert die Art, wie dieser Typ in Debuggerfenstern angezeigt wird. Wenn Sie eine Variable mit einem Proxy oder einem Ersatztyp anzeigen, wird der Proxy stellvertretend für den ursprünglichen Typ im Anzeigefenster des Debuggers angezeigt . Im Debuggervariablenfenster werden nur die öffentlichen Member des Proxytyps angezeigt. Private Member werden nicht angezeigt.  
  
## <a name="using-the-debuggerdisplayattribute"></a>Verwenden des DebuggerDisplayAttribute-Konstruktors  

Der <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A>-Konstruktor verfügt über ein einziges Argument: Eine Zeichenfolge, die in der Wertspalte für Instanzen des Typs angezeigt wird. Diese Zeichenfolge kann geschweifte Klammern ({ und }) enthalten. Der Text innerhalb von Klammern wird als Ausdruck ausgewertet. Beispielsweise verursacht der folgende C#-Code, dass „Count = 4“ angezeigt wird, wenn das Pluszeichen (+) angeklickt wird, um die Debuggeranzeige für eine Instanz von `MyHashtable` anzuzeigen.  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

Attribute, die auf Eigenschaften angewendet werden, auf die im Ausdruck verwiesen wird, werden nicht verarbeitet. Für den C#-Compiler ist ein allgemeiner Ausdruck zugelassen, der nur über impliziten Zugriff auf diesen Verweis auf die aktuelle Instanz des Zieltyps verfügt. Der Ausdruck ist begrenzt, er hat keinen Zugriff auf Aliase, lokale Variablen oder Zeiger. In C#-Code können Sie einen allgemeinen Ausdruck zwischen den Klammern verwenden, der nur über impliziten Zugriff auf den `this`-Zeiger für die aktuelle Instanz des Zieltyps verfügt.

Wenn bei einem C#-Objekt beispielsweise `ToString()` überschrieben wurde, ruft der Debugger die Überschreibung auf und zeigt deren Ergebnisse anstelle des standardmäßigen `{<typeName>}.` an. Wenn Sie also `ToString()` überschrieben haben, müssen Sie <xref:System.Diagnostics.DebuggerDisplayAttribute> nicht verwenden. Wenn Sie beides verwenden, hat das <xref:System.Diagnostics.DebuggerDisplayAttribute>-Attribut Vorrang gegenüber der `ToString()`-Überschreibung.

## <a name="using-the-debuggerbrowsableattribute"></a>Verwenden von DebuggerBrowsableAttribute

 Wenden Sie <xref:System.Diagnostics.DebuggerBrowsableAttribute> auf ein Feld oder eine Eigenschaft an, um anzugeben, wie das Feld oder die Eigenschaft im Debuggerfenster angezeigt werden soll. Der Konstruktor für dieses Attribut nimmt einen der <xref:System.Diagnostics.DebuggerBrowsableState>-Enumerationswerte an, die einen der folgenden Zustände angeben:

- <xref:System.Diagnostics.DebuggerBrowsableState.Never> gibt an, dass das Element nicht im Datenfenster angezeigt wird.  Verwenden Sie diesen Wert beispielsweise für den <xref:System.Diagnostics.DebuggerBrowsableAttribute> eines Felds, um das Feld aus der Hierarchie zu entfernen. Das Feld wird nicht angezeigt, wenn Sie den einschließenden Typ erweitern, indem Sie auf das Pluszeichen (+) für die Typinstanz klicken.

- <xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> gibt an, dass das Element angezeigt, aber nicht standardmäßig erweitert wird.  Dies ist das Standardverhalten.

- <xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> gibt an, dass das Element selbst nicht angezeigt wird. Seine enthaltenen Objekte werden jedoch angezeigt, wenn es sich bei diesen um Arrays oder Sammlungen handelt.

> [!NOTE]
> <xref:System.Diagnostics.DebuggerBrowsableAttribute> wird von Visual Basic in .NET Framework-Version 2.0 nicht unterstützt.

Das folgende Codebeispiel veranschaulicht die Verwendung von <xref:System.Diagnostics.DebuggerBrowsableAttribute>, um zu verhindern, dass die ihm folgende Eigenschaft im Debugfenster für die Klasse angezeigt wird.

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a>Verwenden von DebuggerTypeProxy

 Verwenden Sie das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>-Attribut, wenn Sie die Debuggingansicht eines Typs erheblich und grundlegend ändern müssen, ohne den Typ selbst zu ändern. Das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>-Attribut wird verwendet, um einen Anzeigeproxy für einen Typ anzugeben. Dadurch wird es einem Entwickler ermöglicht, die Ansicht des Typs anzupassen.  Dieses Attribut kann genau wie <xref:System.Diagnostics.DebuggerDisplayAttribute> auf Assemblyebene verwendet werden. In diesem Fall gibt die <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A>-Eigenschaft den Typ an, für den der Proxy verwendet wird. Es wird empfohlen, dass das Attribut einen privaten geschachtelten Typ angibt, der innerhalb des Typs auftritt, auf den das Attribut angewendet wird.  Eine Ausdrucksauswertung, die Überprüfungen für die Ansichten von Typen für dieses Attribut unterstützt, wenn ein Typ angezeigt wird. Wenn das Attribut gefunden wird, ersetzt die Ausdrucksauswertung den Anzeigeproxytyp für den Typ, auf den das Attribut angewendet wird.

 Wenn <xref:System.Diagnostics.DebuggerTypeProxyAttribute> vorhanden ist, werden im Debuggervariablenfenster nur die öffentlichen Member des Proxytyps angezeigt. Private Member werden nicht angezeigt. Das Verhalten des Datenfensters wird durch von Attributen erweiterte Ansichten nicht verändert.

 Um unnötige Leistungseinbußen zu vermeiden, werden Attribute des Anzeigeproxys nicht verarbeitet, bis das Objekt erweitert wurde. Dies geschieht entweder, indem der Benutzer auf das Pluszeichen (+) neben dem Typ im Datenfenster klickt, oder durch Anwenden des <xref:System.Diagnostics.DebuggerBrowsableAttribute>-Attributs. Aus diesem Grund wird empfohlen, keine Attribute auf den Anzeigetyp anzuwenden. Attribute können und sollen im Text des Anzeigetyps angewendet werden.

 Das folgende Codebeispiel veranschaulicht die Verwendung von <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, um einen Typ anzugeben, der als Debuggeranzeigeproxy verwendet werden soll.

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a>Beispiel

### <a name="description"></a>BESCHREIBUNG

Das folgende Codebeispiel kann in Visual Studio angezeigt werden, um die Ergebnisse der Anwendung der <xref:System.Diagnostics.DebuggerDisplayAttribute> <xref:System.Diagnostics.DebuggerBrowsableAttribute> Attribute, und anzuzeigen <xref:System.Diagnostics.DebuggerTypeProxyAttribute> .

### <a name="code"></a>Code

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>
