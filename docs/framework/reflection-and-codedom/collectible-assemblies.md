---
title: Entladbare Assemblys für die dynamische Typgenerierung
description: Hier erfahren Sie mehr über die ersten Schritte mit entladbaren Assemblys für die dynamische Typgenerierung in .NET. Informieren Sie sich über die Lebensdauer und Einschränkungen der entladbaren Assemblys.
ms.date: 08/29/2017
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
ms.openlocfilehash: 4981b93dbd49a6da96740bebed0f2ed7b89036c8
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475124"
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>Entladbare Assemblys für die dynamische Typgenerierung

Bei *entladbaren Assemblys* handelt es sich um dynamische Assemblys, die entladen werden können, ohne die Anwendungsdomäne zu entladen, in der sie erstellt wurden. Der verwaltete und nicht verwaltete Speicher, der von einer entladbaren Assembly und den darin enthaltenen Typen verwendet wurde, kann wieder freigegeben werden. Informationen wie der Name der Assembly werden aus den internen Tabellen entfernt.

Verwenden Sie zum Aktivieren der Entladung das <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType>-Flag, wenn Sie eine dynamische Assembly erstellen. Die Assembly ist flüchtig (d.h. sie kann nicht gespeichert werden) und unterliegt den Einschränkungen, die im Abschnitt [Einschränkungen bei entladbaren Assemblys](#restrictions-on-collectible-assemblies) beschrieben werden. Die Common Language Runtime (CLR) entlädt eine entladbare Assembly automatisch, wenn Sie alle Objekte freigeben, die der Assembly zugeordnet sind. In jeder anderen Hinsicht werden entladbare Assemblys genau wie andere dynamische Assemblys erstellt und verwendet.

## <a name="lifetime-of-collectible-assemblies"></a>Lebensdauer von entladbaren Assemblys

Die Lebensdauer einer entladbaren Assembly wird durch das Vorhandensein der Verweise auf die enthaltenen Typen und auf die Objekte, die aus diesen Typen erstellt werden, gesteuert. Die Common Language Runtime entlädt eine Assembly nicht, solange mindestens eins der folgenden Objekte vorhanden ist (bei `T` handelt es sich um einen beliebigen Typ, der in der Assembly definiert wird):

- Eine Instanz von `T`.

- Eine Instanz eines Arrays von `T`.

- Eine Instanz eines generischen Typs, der über `T` als Typargument verfügt. Dies schließt generische Auflistungen von `T` ein, auch wenn diese Auflistung leer ist.

- Eine Instanz von <xref:System.Type> oder <xref:System.Reflection.Emit.TypeBuilder>, die `T` darstellt.

   > [!IMPORTANT]
   > Sie müssen alle Objekte freigeben, die Teile der Assembly darstellen. Die <xref:System.Reflection.Emit.ModuleBuilder>-Klasse, die `T` definiert, behält einen Verweis auf <xref:System.Reflection.Emit.TypeBuilder> bei, und das <xref:System.Reflection.Emit.AssemblyBuilder>-Objekt behält einen Verweis auf <xref:System.Reflection.Emit.ModuleBuilder> bei. Die Verweise auf diese Objekte müssen ebenfalls freigegeben werden. Auch das Vorhandensein einer <xref:System.Reflection.Emit.LocalBuilder>- oder <xref:System.Reflection.Emit.ILGenerator>-Klasse, die bei der Erstellung von `T` verwendet werden, verhindert das Entladen.

- Ein statischer Verweis auf `T` durch einen anderen dynamisch definierten `T1`-Typ, der für ausgeführten Code weiterhin erreichbar ist. `T1` kann beispielsweise von `T` abgeleitet werden, oder `T` kann den Typ eines Parameters in einer Methode von `T1` darstellen.

- Ein **ByRef**-Modifizierer für ein statisches Feld, das zu `T` gehört.

- Eine <xref:System.RuntimeTypeHandle>-, <xref:System.RuntimeFieldHandle>- oder <xref:System.RuntimeMethodHandle>-Struktur, die auf `T` oder eine Komponente von `T` verweist.

- Eine Instanz eines beliebigen Reflektionsobjekts, das indirekt oder direkt verwendet werden kann, um auf das <xref:System.Type>-Objekt zuzugreifen, das `T` darstellt. Das <xref:System.Type>-Objekt für `T` kann beispielsweise von einem Arraytyp abgerufen werden, dessen Elementtyp `T` ist, oder von einem generischen Typ mit `T` als Typargument.

- Eine `M`-Methode in der Aufrufliste eines beliebigen Threads, bei der `M` eine Methode von `T` oder eine Methode auf Modulebene darstellt, die in der Assembly definiert ist.

- Ein Delegat von einer statischen Methode, der in einem Modul der Assembly definiert wird.

Wenn ein Element aus dieser Liste für einen Typ oder eine Methode in der Assembly vorhanden ist, kann die Runtime die Assembly nicht entladen.

> [!NOTE]
> Die Runtime entlädt die Assembly nicht, bevor Finalizer für alle Elemente in der Liste ausgeführt wurden.

Zum Nachverfolgen der Lebensdauer sollte ein konstruierter generischer Typ wie `List<int>` (in C#) oder `List(Of Integer)` (in Visual Basic), der bei der Generierung einer entladbaren Assembly erstellt und verwendet wird, entweder in der Assembly definiert werden, die die generische Typdefinition enthält, oder in einer Assembly, die die Definition von einem seiner Typargumente enthält. Die Assembly, die verwendet wird, stellt ein Implementierungsdetail dar und unterliegt Änderungen.

## <a name="restrictions-on-collectible-assemblies"></a>Einschränkungen bei entladbaren Assemblys

Für entladbare Assemblys gelten folgende Einschränkungen:

- **Statische Verweise:** Die Typen in einer gewöhnlichen dynamischen Assembly können keine statischen Verweise auf Typen enthalten, die in einer entladbaren Assembly definiert sind. Wenn Sie beispielsweise einen normalen Typ definieren, der von einem Typ in einer entladbaren Assembly erbt, wird eine <xref:System.NotSupportedException>-Ausnahme ausgelöst. Ein Typ in einer entladbaren Assembly kann statische Verweise auf einen Typ in einer anderen entladbaren Assembly enthalten, dadurch wird jedoch die Lebensdauer der Assembly, auf die verweisen wird, auf die Lebensdauer der verweisenden Assembly erweitert.

- **COM-Interop:** In einer entladbaren Assembly können keine COM-Schnittstellen definiert werden, und Instanzen von Typen in einer entladbaren Assembly können nicht in COM-Objekte konvertiert werden. Ein Typ in einer entladbaren Assembly kann nicht als COM Callable Wrapper (CCW) oder Runtime Callable Wrapper (RCW) verwendet werden. Typen in entladbaren Assemblys können jedoch Objekte verwenden, die COM-Schnittstellen implementieren.

- **Plattformaufrufe:** Methoden mit dem <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut können nicht kompiliert werden, wenn diese in einer entladbaren Assembly deklariert werden. Die <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType>-Anweisung kann nicht in der Implementierung eines Typs in einer entladbaren Assembly verwendet werden, und solche Typen können nicht an nicht verwalteten Code gemarshallt werden. Sie können jedoch Aufrufe in nativem Code durchführen, indem Sie einen Einstiegspunkt verwenden, der in einer nicht entladbaren Assembly deklariert ist.

- **Marshalling:** Objekte (insbesondere Delegate), die in entladbaren Assemblys definiert sind, können nicht gemarshallt werden. Diese Einschränkung gilt für alle flüchtig ausgegebenen Typen.

- **Laden von Assemblys:** Die Reflexionsausgabe stellt den einzigen Mechanismus dar, der zum Laden von entladbaren Assemblys unterstützt wird. Assemblys, die mithilfe einer anderen Methode zum Laden von Assemblys geladen werden, können nicht entladen werden.

- **Kontextgebundene Objekte:** Kontextstatische Variablen werden nicht unterstützt. Typen in einer entladbaren Assembly können <xref:System.ContextBoundObject> nicht erweitern. Der Code in entladbaren Assemblys kann jedoch in kontextgebundenen Objekten verwendet werden, die an anderer Stelle definiert werden.

- **Threadstatische Daten:** Threadstatische Variablen werden nicht unterstützt.

## <a name="see-also"></a>Siehe auch

- [Ausgeben von dynamischen Methoden und Assemblys](emitting-dynamic-methods-and-assemblies.md)
