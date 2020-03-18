---
title: -platform (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 5150e871d75c3c34dab10f10cdac3d8322d7a834
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70849867"
---
# <a name="-platform-c-compiler-options"></a>-platform (C#-Compileroptionen)

Gibt an, welche Version der Common Language Runtime (CLR) die Assembly ausführen kann.

## <a name="syntax"></a>Syntax

```console
-platform:string
```

## <a name="parameters"></a>Parameter

`string` \
anycpu (Standard), anycpu32bitpreferred, ARM, x64, x86, oder Itanium.

## <a name="remarks"></a>Hinweise

- **anycpu** (Standard) kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform. Ihre Anwendung wird nach Möglichkeit als 64-Bit-Prozess ausgeführt und wechselt zurück zu 32-Bit, wenn nur dieser Modus verfügbar ist.

- **anycpu32bitpreferred** kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform. Die Anwendung wird auf Systemen, die sowohl 64-Bit- als auch 32-Bit-Anwendungen unterstützen, im 32-Bit-Modus ausgeführt. Sie können diese Option nur für Projekte angeben, die auf .NET Framework 4.5 ausgerichtet sind.

- **ARM** kompiliert Ihre Assembly für die Ausführung auf einem Computer mit einem ARM-Prozessor (Advanced RISC-Computer).

- **ARM64** kompiliert Ihre Assembly für die Ausführung durch die 64-Bit-CLR auf einem Computer mit einem Advanced RISC Machine-Prozessor (ARM), der den A64-Anweisungssatz unterstützt.

- **x64** kompiliert Ihre Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Befehlssatz unterstützt.

- **x86** kompiliert die Assembly für die 32-Bit-CLR (Common Language Runtime), die mit x86 kompatibel ist.

- **Itanium** kompiliert Ihre Assembly für die Ausführung durch die 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.

Auf einem 64-Bit-Windows-Betriebssystem:

- Mit **-platform:x86** kompilierte Assemblys werden in der 32-Bit-CLR unter WOW64 ausgeführt.

- Eine mit **-platform:anycpu** kompilierte DLL wird in derselben CLR wie der Prozess, in den sie geladen wurde, ausgeführt.

- Ausführbare Dateien, die mit **-platform:anycpu** kompiliert werden, werden in der 64-Bit-CLR ausgeführt.

- Ausführbare Dateien, die mit **-platform:anycpu32bitpreferred** kompiliert werden, werden in der 32-Bit-CLR ausgeführt.

Die Einstellung **anycpu32bitpreferred** gilt nur für ausführbare Dateien (.exe) und erfordert .NET Framework 4.5.

Weitere Informationen zum Entwickeln einer Anwendung, die auf einem 64-Bit-Windows-Betriebssystem ausgeführt werden soll, finden Sie unter [64-Bit-Anwendungen](../../../framework/64-bit-apps.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie die Seite **Eigenschaften** für das Projekt.

2. Klicken Sie auf die Eigenschaftenseite **Build** .

3. Ändern Sie die Eigenschaft **Zielplattform**, und aktivieren oder deaktivieren Sie für Projekte, die auf .NET Framework 4.5 ausgerichtet sind, das Kontrollkästchen **32-Bit bevorzugen**.

> [!NOTE]
> `-platform` ist in der Entwicklungsumgebung in Visual C# Express nicht verfügbar.

Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die Option **-platform** verwenden können, um anzugeben, dass die Anwendung von der 64-Bit-CLR auf einem 64-Bit-Windows-Betriebssystem ausgeführt werden soll.

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
