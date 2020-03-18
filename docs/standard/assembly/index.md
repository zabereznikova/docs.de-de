---
title: Assemblys in .NET
ms.date: 08/15/2019
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
helpviewer_keywords:
- dynamic assemblies
- security [.NET Framework], boundaries
- boundaries of assemblies
- assemblies [.NET Framework], about
- assemblies [.NET Framework], boundaries
- reference scope boundaries
- assemblies [.NET Framework]
- version boundaries
- type boundaries
ms.openlocfilehash: f85fef37ac952c91ac73570f26d80d8a46f4eedf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156504"
---
# <a name="assemblies-in-net"></a>Assemblys in .NET

Assemblys bilden die Grundlage für die Bereitstellung, die Versionskontrolle, die Wiederverwendung, die Festlegung des Aktivierungsumfangs und die Sicherheitsberechtigungen für .NET-basierte Anwendungen. Eine Assembly ist eine Auflistung von Typen und Ressourcen, die so erstellt wurden, dass sie zusammenarbeiten und eine logische funktionelle Einheit bilden. Assemblys sind ausführbare Dateien ( *.exe*) oder Dynamic Link Library-Dateien ( *.dll*) und bilden die Bausteine von .NET-Anwendungen. Sie stellen der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt.

In .NET Core und .NET Framework können Sie eine Assembly entweder aus einer oder aus mehreren Quellcodedateien erstellen. In .NET Framework können Assemblys ein Modul oder mehrere Module umfassen. Dies macht es möglich, größere Projekte so zu planen, dass mehrere Entwickler an verschiedenen Quellcodedateien oder Modulen arbeiten, die anschließend in einer einzigen Assembly kombiniert werden. Weitere Informationen zu Modulen finden Sie unter [Vorgehensweise: Erstellen einer Assembly aus mehreren Dateien](../../framework/app-domains/build-multifile-assembly.md).

Assemblys verfügen über folgende Eigenschaften:

- Assemblys werden als *EXE*- oder *DLL*-Dateien implementiert.

- Für Bibliotheken, die auf .NET Framework ausgerichtet sind, können Sie eine Assembly für mehrere Anwendungen freigeben, indem Sie sie im [globalen Assemblycache](../../framework/app-domains/gac.md) ablegen. Sie müssen den Assemblys starke Namen geben, bevor Sie sie zum globalen Assemblycache hinzufügen können. Weitere Informationen finden Sie unter [Assemblys mit starken Namen](strong-named.md).

- Assemblys werden nur in den Arbeitsspeicher geladen, wenn sie erforderlich sind. Wenn sie nicht verwendet werden, werden sie auch nicht geladen. Dies bedeutet, dass Assemblys eine effiziente Möglichkeit zur Verwaltung von Ressourcen in größeren Projekten sein können.

- Sie können mithilfe der Reflektion programmgesteuert Informationen zu einer Assembly abrufen. Weitere Informationen finden Sie unter [Reflektion (C#)](../../csharp/programming-guide/concepts/reflection.md) oder [Reflektion (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).

- Sie können Assemblys laden, um sie nur zu untersuchen, indem Sie die <xref:System.Reflection.MetadataLoadContext>-Klasse in .NET Core und die Methode <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> in .NET Core und .NET Framework verwenden.

## <a name="assemblies-in-the-common-language-runtime"></a>Assemblys in der Common Language Runtime (CLR)

Assemblys stellen der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen von Typimplementierungen benötigt. Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.

Eine Assembly definiert die folgenden Informationen:

- Code, der von der Common Language Runtime ausgeführt wird. Beachten Sie, dass jede Assembly nur über einen Einstiegspunkt (`DllMain`, `WinMain` oder `Main`) verfügen kann.

- Sicherheitsgrenze. Eine Assembly ist die Einheit, bei der Berechtigungen angefordert und erteilt werden. Weitere Informationen über Sicherheitsgrenzen in Assemblys finden Sie unter [Überlegungen zur Assemblysicherheit](security-considerations.md).

- Typgrenze. Die Identität jedes Typs enthält den Namen der Assembly, in der dieser sich befindet. Wenn der Typ `MyType` in den Gültigkeitsbereich einer Assembly geladen wird, ist dieser nicht derselbe wie der Typ `MyType`, der in den Gültigkeitsbereich einer anderen Assembly geladen wurde.

- Grenzen für Gültigkeitsbereiche. Das [Assemblymanifest](#assembly-manifest) enthält Metadaten, die für das Auflösen von Typen und die Bereitstellung angeforderter Ressourcen verwendet werden. Das Manifest gibt die Typen und Ressourcen an, die außerhalb der Assembly verfügbar gemacht werden sollen, und listet andere Assemblys auf, von denen es abhängig ist. MSIL-Code (Microsoft Intermediate Language) in einer übertragbaren ausführbaren Datei (Portable Executable, PE) wird nur ausgeführt, wenn diesem ein [Assemblymanifest](#assembly-manifest) zugeordnet wurde.

- Versionsgrenze. Die Assembly ist die kleinste versionierbare Einheit in der Common Language Runtime. Alle Typen und Ressourcen in derselben Assembly werden als eine Einheit versioniert. Das [Assemblymanifest](#assembly-manifest) beschreibt die von Ihnen für abhängige Assemblys angegebenen Versionsabhängigkeiten. Weitere Informationen über die Versionsverwaltung finden Sie unter [Assemblyversionsverwaltung](versioning.md).

- Bereitstellungseinheit. Beim Starten einer Anwendung müssen nur die von der Anwendung zu Beginn aufgerufenen Assemblys vorhanden sein. Andere Assemblys, z. B. Assemblys mit Lokalisierungsressourcen oder Hilfsklassen, können bei Bedarf abgerufen werden. Dadurch ist die App beim ersten Herunterladen einfach und schlank. Weitere Informationen über die Bereitstellung von Assemblys finden Sie unter [Bereitstellen von Anwendungen](../../framework/deployment/index.md).

- Einheit für die parallele Ausführung. Weitere Informationen über das Ausführen mehrerer Versionen einer Assembly finden Sie unter [Assemblys und parallele Ausführung](side-by-side-execution.md).

## <a name="create-an-assembly"></a>Erstellen einer Assembly

Assemblys können statisch oder dynamisch sein. Statische Assemblys werden auf dem Datenträger in PE-Dateien (Portable Executable, übertragbare ausführbare Datei) gespeichert. Statische Assemblys können Schnittstellen, Klassen und Ressourcen wie Bitmaps, JPEG-Dateien und andere Ressourcendateien beinhalten. Sie können außerdem dynamische Assemblys erstellen, die direkt vom Arbeitsspeicher aus ausgeführt und vor der Ausführung nicht auf dem Datenträger gespeichert werden. Dynamische Assemblys können nach ihrer Ausführung auf dem Datenträger gespeichert werden.

Beim Erstellen von Assemblys stehen Ihnen verschiedene Möglichkeiten zur Verfügung: Sie können Entwicklungstools wie Visual Studio verwenden, die *DLL*- und *EXE*-Dateien erstellen können. Mit den Tools im Windows SDK können Sie Assemblys mit Modulen erstellen, die in anderen Entwicklungsumgebungen erstellt wurden. Außerdem können Sie dynamische Assemblys auch mit Common Language Runtime-APIs wie <xref:System.Reflection.Emit?displayProperty=nameWithType> erstellen.

Sie können Assemblys kompilieren, indem Sie sie in Visual Studio, über Tools für die .NET Core-Befehlszeilenschnittstelle oder .NET Framework-Assemblys mit einem Befehlszeilencompiler erstellen. Weitere Informationen zum Erstellen von Assemblys mit der .NET Core-CLI finden Sie unter [Übersicht über die .NET Core-CLI](../../core/tools/index.md). Informationen zum Erstellen von Assemblys mit einem Befehlszeilencompiler finden Sie unter [Erstellen über die Befehlszeile mit csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) für C# oder [Erstellen über die Befehlszeile](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) für Visual Basic.

> [!NOTE]
> Sie können eine Assembly in Visual Studio erstellen, indem Sie im Menü **Build** auf die Option **Build** klicken.

## <a name="assembly-manifest"></a>Assemblymanifest

Jede Assembly enthält eine *Assemblymanifestdatei*. Ähnlich wie ein Inhaltsverzeichnis enthält das Assemblymanifest Folgendes:

- Die Identität der Assembly (Name und Version).

- Eine Dateitabelle, die alle anderen Dateien beschreibt, aus denen die Assembly besteht, z. B. weitere Assemblys, die Sie erstellt haben, von denen Ihre *EXE*- oder *DLL*-Datei abhängig ist, oder sogar Bitmap- oder Infodateien.

- Eine *Assemblyverweisliste*, also eine Liste aller externen Abhängigkeiten, z. B. *DLL*-Dateien oder andere Dateien. Assemblyverweise enthalten Verweise auf globale und private Objekte. Globale Objekte stehen für alle weiteren Anwendungen zur Verfügung. In .NET Core werden globale Objekte an eine bestimmte .NET Core-Runtime gekoppelt. In .NET Framework befinden sich globale Objekte im globalen Assemblycache. *System. IO. dll* ist ein Beispiel für eine Assembly im globalen Assemblycache. Private Objekte müssen sich auf Verzeichnisebene oder unterhalb des Verzeichnisses befinden, in dem die App installiert ist.

Da Assemblys Informationen zu Inhalt, Versionsverwaltung und Abhängigkeiten enthalten, sind Anwendungen, die die Assemblys verwenden, nicht von externen Quellen wie der Registrierung auf Windows-Systemen abhängig, um ordnungsgemäß zu funktionieren. Assemblys reduzieren *DLL*-Konflikte, verbessern die Zuverlässigkeit und vereinfachen die Bereitstellung Ihrer Anwendungen. In vielen Fällen können Sie eine .NET-basierte Anwendung einfach durch Kopieren der Dateien auf den Zielcomputer installieren. Weitere Informationen finden Sie unter [Assemblymanifest](manifest.md).

## <a name="add-a-reference-to-an-assembly"></a>Hinzufügen eines Verweises auf eine Assembly

Damit Sie eine Assembly in einer Anwendung verwenden können, müssen Sie einen Verweis auf diese hinzufügen. Sobald auf eine Assembly verwiesen wird, sind alle zugänglichen Typen, Eigenschaften, Methoden und andere Member ihrer Namespaces für Ihre Anwendung verfügbar, als wäre ihr Code Teil der Quelldatei.

> [!NOTE]
> Die meisten Assemblys der .NET-Klassenbibliothek werden automatisch referenziert. Wenn nicht automatisch auf eine Systemassembly verwiesen wird, können Sie für .NET Core einen Verweis auf das NuGet-Paket hinzufügen, in dem die Assembly enthalten ist. Verwenden Sie entweder den NuGet-Paket-Manager in Visual Studio, oder fügen Sie dem *CSPROJ*- oder dem *VBPROJ*-Projekt ein [\<PackageReference>](../../core/tools/dependencies.md#the-packagereference-element)-Element für die Assembly hinzu. In .NET Framework können Sie über das Dialogfeld **Verweis hinzufügen** in Visual Studio einen Verweis auf die Assembly hinzufügen, oder Sie verwenden die Befehlszeilenoption `-reference` für den [C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md)- oder [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md)-Compiler.

In C# können Sie zwei Versionen derselben Assembly in einer einzigen Anwendung verwenden. Weitere Informationen finden Sie unter [extern-Alias](../../csharp/language-reference/keywords/extern-alias.md).

## <a name="related-content"></a>Verwandter Inhalt

|Titel|Beschreibung|
|-----------|-----------------|
|[Assemblyinhalte](contents.md)|Elemente, aus denen die Assembly besteht|
|[Assemblymanifest](manifest.md)|Die Daten im Assemblymanifest und wie diese in Assemblys gespeichert werden|
|[Globaler Assemblycache](../../framework/app-domains/gac.md)|Wie der globale Assemblycache Assemblys speichert und verwendet|
|[Assemblys mit starken Namen](strong-named.md)|Die Eigenschaften von Assemblys mit starken Namen|
|[Überlegungen zur Assemblysicherheit](security-considerations.md)|Funktionsweise der Sicherheitsmechanismen von Assemblys|
|[Assemblyversionsverwaltung](versioning.md)|Übersicht über die Versionsverwaltungsrichtlinie von .NET Framework|
|[Assemblypositionierung](../../framework/app-domains/assembly-placement.md)|Die Positionierung von Assemblys|
|[Assemblys und parallele Ausführung](side-by-side-execution.md)|Das gleichzeitige Verwenden mehrerer Versionen der Runtime oder einer Assembly|
|[Ausgeben von dynamischen Methoden und Assemblys](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|Erstellen von dynamischen Assemblys|
|[So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|So löst .NET Framework zur Laufzeit Assemblyverweise auf|

## <a name="reference"></a>Referenz

<xref:System.Reflection.Assembly?displayProperty=nameWithType>

## <a name="see-also"></a>Siehe auch

- [.NET-Assemblydateiformat](file-format.md)
- [Friend-Assemblys](friend.md)
- [Verweisassemblys](reference-assemblies.md)
- [How to: Laden und Entladen von Assemblys](load-unload.md)
- [How to: Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core](unloadability.md)
- [How to: Bestimmen, ob eine Datei eine Assembly ist](identify.md)
