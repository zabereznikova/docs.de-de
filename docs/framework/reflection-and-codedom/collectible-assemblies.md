---
title: "Entladbare Assemblys für die dynamische typgenerierung"
description: 
ms.date: 08/29/2017
ms.prod: .net
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c9a613f4cc13c3e4189a59ace2e05d01d1bcb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>Entladbare Assemblys für die dynamische typgenerierung

*Entladbare Assemblys* sind dynamische Assemblys, die entladen werden können, ohne Entladen der Anwendungsdomäne, in dem sie erstellt wurden. Alle verwaltetem und unverwaltetem Speicher verwendet, die durch eine entladbare Assembly und die darin enthaltenen Typen kann freigegeben werden. Informationen wie z. B. der Name der Assembly wird aus internen Tabellen entfernt.

Verwenden Sie zum Aktivieren der Entladung der <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> kennzeichnen, wenn Sie eine dynamische Assembly erstellen. Die Assembly ist flüchtig (d. h., es kann nicht gespeichert werden) und im beschriebenen Einschränkungen unterliegt den [Beschränkungen entladbarer Assemblys](#restrictions-on-collectible-assemblies) Abschnitt. Die common Language Runtime (CLR) entlädt entladbare Assemblys automatisch, wenn Sie alle Objekte, die mit der Assembly verknüpfte freigeben. In jeder anderen Hinsicht entladbarer Assemblys erstellt und auf die gleiche Weise wie andere dynamische Assemblys verwendet.

## <a name="lifetime-of-collectible-assemblies"></a>Lebensdauer entladbarer Assemblys

Die Lebensdauer einer entladbare Assembly wird gesteuert, indem das Vorhandensein von Verweisen auf die darin enthaltenen Typen und die Objekte, die von diesen Typen erstellt werden. Die common Language Runtime entladen eine Assembly nicht, solange mindestens einer der folgenden vorhanden (`T` ist jeder Typ, der in der Assembly definiert ist): 

- Eine Instanz von `T`.

- Eine Instanz eines Arrays von `T`.
 
- Eine Instanz eines generischen Typs, der verfügt `T` als eines seiner Typargumente. Dies schließt generische Sammlungen des `T`, selbst wenn diese Auflistung leer ist.

- Eine Instanz von <xref:System.Type> oder <xref:System.Reflection.Emit.TypeBuilder> darstellt, die `T`. 

   > [!IMPORTANT]
   > Sie müssen alle Objekte freigeben, die Teile der Assembly darstellen. Die <xref:System.Reflection.Emit.ModuleBuilder> , definiert `T` behält einen Verweis auf die <xref:System.Reflection.Emit.TypeBuilder>, und die <xref:System.Reflection.Emit.AssemblyBuilder> Objekt verwaltet einen Verweis auf die <xref:System.Reflection.Emit.ModuleBuilder>, sodass Verweise auf diese Objekte freigegeben werden müssen. Auch das Vorhandensein eines eine <xref:System.Reflection.Emit.LocalBuilder> oder ein <xref:System.Reflection.Emit.ILGenerator> verwendet bei der Erstellung von `T` wird verhindert, dass entladen.

- Ein statischer Verweis auf `T` von einem anderen dynamisch definierte Typ `T1` , die durch das Ausführen von Code weiterhin erreichbar ist. Beispielsweise `T1` abgeleitet möglicherweise `T`, oder `T` möglicherweise, dass der Typ eines Parameters in einer Methode des `T1`.
 
- Ein **ByRef** in einem statischen Feld, das zu gehört `T`.

- Ein <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, oder <xref:System.RuntimeMethodHandle> bezieht, die sich auf `T` oder mit einer Komponente von `T`.

- Eine Instanz eines Reflektionsobjekts, die indirekt verwendet werden konnte oder direkt für den Zugriff auf die <xref:System.Type> Objekt, das darstellt `T`. Z. B. die <xref:System.Type> -Objekt für `T` abgerufen werden kann, von einem Arraytyp, dessen Elementtyp `T`, oder aus einem generischen Typ, der verfügt `T` als Typargument. 

- Eine Methode `M` in der Aufrufliste für einen beliebigen Thread, in dem `M` ist eine Methode `T` oder eine auf Modulebene-Methode, die in der Assembly definiert ist.

- Ein Delegat auf eine statische Methode, die in einem Modul der Assembly definiert ist.

Wenn nur ein Element aus dieser Liste für nur einen Typ oder eine Methode in der Assembly vorhanden ist, kann die Common Language Runtime die Assembly nicht entfernen.

> [!NOTE]
> Die Common Language Runtime wird nicht tatsächlich die Assembly entladen, bis für alle Elemente in der Liste Finalizer ausgeführt haben.

Zwecks Überwachung Lebensdauer einen konstruierten generischen Typ wie z. B. `List<int>` (in c#) oder `List(Of Integer)` (in Visual Basic) ist, erstellt und verwendet die Generierung einer entladbare Assembly gilt wurden entweder in der Assembly definiert, enthält die generische Typdefinition oder in einer Assembly enthält, die die Definition eines seiner Typargumente. Die genaue Assembly, die verwendet wird, ist ein Implementierungsdetail und kann geändert.
 
## <a name="restrictions-on-collectible-assemblies"></a>Einschränkungen für entladbare Assemblys

Entladbare Assemblys gelten die folgenden Einschränkungen: 

- **Der Code statische Verweise**   
  Typen in eine gewöhnliche dynamische Assembly sind keine statische Verweise auf Typen, die in einer entladbare Assembly definiert sind. Wenn Sie einen normalen Typ definieren, die von einem Typ in einer entladbare Assembly erbt beispielsweise eine <xref:System.NotSupportedException> Ausnahme wird ausgelöst. Ein Typ in einer entladbare Assembly kann Code statische Verweise auf einen Typ in einer anderen entladbare Assembly haben, aber dies erweitert die Lebensdauer der Assembly, die die Lebensdauer der verweisenden Assembly verwiesen wird.

- **COM-interop**   
   Keine COM-Schnittstellen können innerhalb einer entladbaren Assembly definiert werden, und keine Instanzen von Typen in einer entladbare Assembly in COM-Objekte konvertiert werden können. Ein Typ in einer entladbare Assembly kann nicht als COM callable Wrapper (CCW) oder Common Language Runtime callable Wrapper (RCW) dienen. Allerdings können Typen in Assemblys entladbarer Objekte, die COM-Schnittstellen implementieren.

- **Plattformaufruf**   
   Methoden, auf die <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut kann nicht kompiliert werden, wenn sie in einer entladbare Assembly deklariert werden. Die <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> Anweisung kann nicht in der Implementierung eines Typs in eine entladbare Assembly verwendet werden, und solche Typen können nicht zu nicht verwaltetem Code gemarshallt werden. Allerdings können Sie in systemeigenen Code mit Aufrufen eines Einstiegspunkts, das in einer nicht-entladbare Assembly deklariert ist.
 
- **Marshalling**   
   Objekte (in bestimmten, Delegaten), die in entladbare Assemblys definiert sind, können nicht gemarshallt werden. Dies ist eine Einschränkung für alle flüchtigen ausgegebenen Typen.

- **Das Laden einer Assembly**   
   Reflektionsausgabe ist der einzige Mechanismus, der zum Laden von Assemblys entladbare unterstützt wird. Assemblys, die geladen werden, indem Sie jede sonstige Form von das Laden einer Assembly können nicht entladen werden.
 
- **Kontext gebundene Objekte**    
   Kontextunabhängige Variablen werden nicht unterstützt. Typen in einer entladbare Assembly können nicht erweitert werden <xref:System.ContextBoundObject>. Jedoch kann Code entladbarer Assemblys verwendet kontextgebundene-Objekte, die definiert, werden an anderer Stelle.

- **Threadstatische Daten**       
   Threadstatische Variablen werden nicht unterstützt.

## <a name="see-also"></a>Siehe auch

[Ausgeben von dynamischen Methoden und Assemblys](emitting-dynamic-methods-and-assemblies.md)
