---
title: Erstellen einer Union in C/C++ mithilfe von Attributen (C#)
description: Hier erfahren Sie, wie Sie in C# mithilfe von Attributen anpassen können, wie Strukturen im Arbeitsspeicher angeordnet werden. In diesem Beispiel wird die Entsprechung einer Union in C/C++ implementiert.
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: 766a070105441630dfd8fecf7b9f68fa6818fe50
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925071"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a>Erstellen einer Union in C/C++ mithilfe von Attributen (C#)

Mithilfe von Attributen können Sie anpassen, wie Strukturen im Arbeitsspeicher angeordnet werden. Sie können z.B. das erstellen, was als eine Union in C/C++ bekannt ist, indem Sie die mit `StructLayout(LayoutKind.Explicit)`- und `FieldOffset`-Attribute verwenden.

## <a name="example"></a>Beispiel

In diesem Codesegment beginnen alle Felder von `TestUnion` an derselben Position im Arbeitsspeicher.

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestUnion
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public byte b;
}
```

## <a name="example"></a>Beispiel

Im Folgenden finden Sie ein weiteres Beispiel, in dem Felder an verschiedenen, explizit festgelegten Orten beginnen.

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestExplicit
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public long lg;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i1;

    [System.Runtime.InteropServices.FieldOffset(4)]
    public int i2;

    [System.Runtime.InteropServices.FieldOffset(8)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(12)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(14)]
    public byte b;
}
```

Die zwei Ganzzahlfelder `i1` und `i2` teilen die gleichen Speicheradressen wie `lg`. Diese Art der Kontrolle über das Strukturlayout ist nützlich, wenn Sie Plattformaufrufe nutzen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- <xref:System.Attribute>
- [C#-Programmierhandbuch](../../index.md)
- [Attribute](../../../../standard/attributes/index.md)
- [Reflektion (C#)](../reflection.md)
- [Attribute (C#)](index.md)
- [Erstellen benutzerdefinierter Attribute (C#)](creating-custom-attributes.md)
- [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](accessing-attributes-by-using-reflection.md)
