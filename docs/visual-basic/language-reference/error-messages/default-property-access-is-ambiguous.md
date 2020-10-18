---
title: Der Standardeigenschaftenzugriff ist nicht eindeutig. Es kann sich um den geerbten Schnittstellenmember "<defaultpropertyname>" der Schnittstelle "<interfacename1>" oder "<defaultpropertyname>" der Schnittstelle "<interfacename2>" handeln.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: b7c4c9c75de1b3777f34a70470b89f323a5699f9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162062"
---
# <a name="bc30686-default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>BC30686: der Standardeigenschaften Zugriff ist zwischen den geerbten Schnittstellenmembern ' \<defaultpropertyname> ' der-Schnittstelle ' \<interfacename1> ' und ' \<defaultpropertyname> ' der-Schnittstelle \<interfacename2> mehrdeutig.

Eine Schnittstelle erbt von zwei Schnittstellen, von denen jede eine Standard Eigenschaft mit demselben Namen deklariert. Der Compiler kann keinen Zugriff auf diese Standard Eigenschaft ohne Qualifizierung auflösen. Dies wird anhand des folgenden Beispiels veranschaulicht.

```vb
Public Interface Iface1
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface2
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface3
    Inherits Iface1, Iface2
End Interface
Public Class testClass
    Public Sub accessDefaultProperty()
        Dim testObj As Iface3
        Dim testInt As Integer = testObj(1)
    End Sub
End Class
```

Wenn Sie angeben `testObj(1)` , versucht der Compiler, ihn in die Default-Eigenschaft aufzulösen. Aufgrund der geerbten Schnittstellen gibt es jedoch zwei mögliche Standardeigenschaften, daher signalisiert der Compiler diesen Fehler.

**Fehler-ID:** BC30686

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Vermeiden Sie das Erben von Membern mit dem gleichen Namen. Wenn im vorherigen Beispiel keines der Member von benötigt, z. b., `testObj` `Iface2` , deklarieren Sie es wie folgt:

  ```vb
  Dim testObj As Iface1
  ```

  \- oder -

- Implementieren Sie die erbende Schnittstelle in einer Klasse. Anschließend können Sie jede der geerbten Eigenschaften mit unterschiedlichen Namen implementieren. Es kann jedoch nur eine der Standardeigenschaften der implementierenden Klasse sein. Dies wird anhand des folgenden Beispiels veranschaulicht.

  ```vb
  Public Class useIface3
      Implements Iface3
      Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop
          ' Insert code to define Get and Set procedures for prop1.
      End Property
      Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop
          ' Insert code to define Get and Set procedures for prop2.
      End Property
  End Class
  ```

## <a name="see-also"></a>Siehe auch

- [Schnittstellen](../../programming-guide/language-features/interfaces/index.md)
