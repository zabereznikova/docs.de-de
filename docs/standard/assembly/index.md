---
title: Assemblys in .NET
ms.date: 07/10/2018
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
ms.openlocfilehash: 09dc44141a4eea7601df3f918e8740efdb99aeda
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666593"
---
# <a name="assemblies-in-net"></a>Assemblys in .NET

Assemblys bilden die Grundlage für die Bereitstellung, die Versionskontrolle, die Wiederverwendung, die Festlegung des Aktivierungsumfangs und die Sicherheitsberechtigungen für eine .NET-basierte Anwendung. Assemblys sind ausführbare Dateien (EXE-Dateien) oder DLL-Dateien, sie bilden die Bausteine von .NET-Anwendungen. Sie stellen der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt. Sie können sich eine Assembly als Sammlung von Typen und Ressourcen vorstellen, die eine logische Funktionalitätseinheit bilden und zusammenarbeiten.

In .NET Core und .NET Framework kann eine Assembly aus einer oder mehreren Quellcodedateien erstellt werden. In .NET Framework können Assemblys ein Modul oder mehrere Module umfassen. Dies macht es möglich, größere Projekte so zu planen, dass verschiedene unabhängige Entwickler an verschiedenen Quellcodedateien oder Modulen arbeiten, die anschließend in einer einzigen Assembly kombiniert werden. Weitere Informationen zu Modulen finden Sie unter [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../framework/app-domains/how-to-build-a-multifile-assembly.md).

Assemblys verfügen über folgende Eigenschaften:

- Assemblys werden als EXE- oder DLL-Dateien implementiert.

- Für Bibliotheken, die auf .NET Framework ausgerichtet sind, können Sie eine Assembly zwischen Anwendungen teilen, indem Sie sie im [globalen Assemblycache](../../framework/app-domains/gac.md) ablegen. Assemblys müssen über einen starken Namen verfügen, bevor sie dem globalen Assemblycache hinzugefügt werden können. Weitere Informationen finden Sie unter [Assemblys mit starkem Namen](../../framework/app-domains/strong-named-assemblies.md).

- Assemblys werden nur in den Arbeitsspeicher geladen, wenn sie erforderlich sind. Wenn sie nicht verwendet werden, werden sie nicht geladen. Dies bedeutet, dass Assemblys eine effiziente Möglichkeit zur Verwaltung von Ressourcen in größeren Projekten sein können.

- Sie können mithilfe der Reflektion programmgesteuert Informationen zu einer Assembly abrufen. Weitere Informationen finden Sie unter [Reflektion (C#)](../../csharp/programming-guide/concepts/reflection.md) oder [Reflektion (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).

- Sie können eine Assembly nur zur Untersuchung laden, indem Sie die <xref:System.Reflection.MetadataLoadContext>-Klasse verwenden.

## <a name="assembly-manifest"></a>Assemblymanifest

Jede Assembly enthält ein *Assemblymanifest*. Ähnlich wie ein Inhaltsverzeichnis enthält das Assemblymanifest Folgendes:

- Die Identität der Assembly (Name und Version).

- Eine Dateitabelle, die alle anderen Dateien beschreibt, aus denen die Assembly besteht, z.B. weitere Assemblys, die Sie erstellt haben, auf denen Ihre EXE- oder DLL-Datei basiert, oder sogar Bitmap- oder Infodateien.

- Eine *Assemblyverweisliste*, eine Liste aller externen Abhängigkeiten, z.B. DLL-Dateien oder andere Dateien, die Ihre Anwendung benötigt, die möglicherweise von einer anderen Person erstellt wurden. Assemblyverweise enthalten Verweise auf globale und private Objekte. Globale Objekte stehen für alle weiteren Anwendungen zur Verfügung. In .NET Core sind diese an eine bestimmte .NET Core-Runtime gekoppelt. In .NET Framework befinden sie sich im globalen Assemblycache. Der Namespace <xref:System.IO?displayProperty=nameWithType> ist ein Beispiel für eine Assembly im globalen Assemblycache. Private Objekte müssen sich in einem Verzeichnis auf derselben Ebene oder unterhalb des Verzeichnisses befinden, in dem die Anwendung installiert ist.

Da Assemblys Informationen zu Inhalt, Versionsverwaltung und Abhängigkeiten enthalten, sind Anwendungen, die die Assemblys verwenden, nicht von Windows-Registrierungswerten abhängig, um ordnungsgemäß zu funktionieren. Assemblys reduzieren DLL-Konflikte, verbessern die Zuverlässigkeit und vereinfachen die Bereitstellung Ihrer Anwendungen. In vielen Fällen können Sie eine .NET-basierte Anwendung einfach durch Kopieren der Dateien auf den Zielcomputer installieren. Weitere Informationen finden Sie unter [Assemblymanifest](../../framework/app-domains/assembly-manifest.md).

## <a name="adding-a-reference-to-an-assembly"></a>Hinzufügen eines Verweises auf eine Assembly

Um eine Assembly zu verwenden, müssen Sie einen Verweis darauf hinzufügen. Als Nächstes können Sie die [using-Direktive](../../csharp/language-reference/keywords/using-directive.md) für C# oder eine [Imports-Anweisung](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) für Visual Basic verwenden, um den Namespace der Elemente auszuwählen, die Sie verwenden möchten. Sobald auf eine Assembly verwiesen und sie importiert wird, sind alle zugänglichen Typen, Eigenschaften, Methoden und anderen Member ihrer Namespaces für Ihre Anwendung verfügbar, als wäre ihr Code Teil der Quelldatei.

> [!NOTE]
> Die meisten Assemblys der .NET-Klassenbibliothek werden automatisch referenziert. In einigen Fällen jedoch kann eine Systemassembly möglicherweise nicht automatisch referenziert werden. In .NET Core können Sie einen Verweis auf das NuGet-Paket mit der Assembly hinzufügen, indem Sie entweder den NuGet-Paket-Manager in Visual Studio verwenden, oder indem Sie dem *.csproj- oder *.vbproj-Projekt ein [\<PackageReference>](../../core/tools/dependencies.md#the-new-packagereference-element)-Element für die Assembly hinzufügen. In .NET Framework können Sie einen Verweis auf die Assembly über das Dialogfeld **Verweis hinzufügen** in Visual Studio hinzufügen, oder Sie verwenden die Befehlszeilenoption `-reference` für den [C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md)- oder [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md)-Compiler.

In C# können Sie auch zwei Versionen derselben Assembly in einer einzigen Anwendung verwenden. Weitere Informationen finden Sie unter [extern-Alias](../../csharp/language-reference/keywords/extern-alias.md).

## <a name="creating-an-assembly"></a>Erstellen einer Assembly

Kompilieren Sie Ihre Anwendung, indem Sie sie in Visual Studio erstellen, indem Sie sie von der Befehlszeile aus mit den CLI-Tools (Command Line Interface) von.NET Core erstellen, oder indem Sie mit einem Befehlszeilencompiler .NET Framework-Assemblys erstellen. Weitere Informationen zum Erstellen von Assemblys mit .NET-CLI-Tools finden Sie unter [Tools für die .NET Core-Befehlszeilenschnittstelle](../../core/tools/index.md). Informationen zum Erstellen von Assemblys mit einem Befehlszeilencompiler finden Sie unter [Erstellen über die Befehlszeile mit csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) für C# und [Erstellen über die Befehlszeile](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) für Visual Basic.

> [!NOTE]
> Sie erstellen eine Assembly in Visual Studio, indem Sie im Menü **Build** die Option **Build** wählen.

## <a name="see-also"></a>Siehe auch

- [.NET-Assemblydateiformat](file-format.md)
- [Assemblys in der Common Language Runtime (CLR)](../../framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Friend-Assemblys](friend-assemblies.md)
- [Vorgehensweise: Laden und Entladen von Assemblys (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)
- [Vorgehensweise: Laden und Entladen von Assemblys (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)
- [Vorgehensweise: Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core](unloadability-howto.md)
- [Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)
- [Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)
