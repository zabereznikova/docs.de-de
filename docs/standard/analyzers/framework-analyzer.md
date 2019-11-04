---
title: Die .NET Security Analyzer – .NET
description: Erfahren Sie, wie Sie die .NET Security Analyzer im Pakt mit den .NET Framework-Analyzern verwenden, um Sicherheitsrisiken zu ermitteln und zu beheben.
author: billwagner
ms.author: wiwagn
ms.date: 01/25/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 03268375739b34a43f38c60fbfd2c993da9f3840
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197962"
---
# <a name="the-net-framework-analyzer"></a>Der .NET Framework Analyzer

Sie können den .NET Framework Analyzer verwenden, um potenzielle Probleme in Ihrem auf .NET Framework basierenden Anwendungscode zu ermitteln. Dieses Analysetool findet mögliche Probleme und schlägt Lösungen zu deren Behebung vor.

Das Analysetool wird interaktiv in Visual Studio ausgeführt, während Sie Code schreiben, oder im Rahmen eines CI-Builds. Sie sollten das Analysetool Ihrem Projekt so früh wie möglich im Entwicklungszyklus hinzufügen. Je früher Sie potenzielle Probleme in Ihrem Code finden, desto einfacher lassen sie sich beheben. Sie können das Tool aber zu jedem Zeitpunkt im Entwicklungszyklus hinzufügen. Es findet Probleme mit vorhandenem Code und warnt bei neuen Problemen, wenn Sie mit der Entwicklung fortfahren.

## <a name="installing-and-configuring-the-net-framework-analyzer"></a>Installieren und Konfigurieren des .NET Framework Analyzers

Die .NET Security Analyzer müssen als NuGet-Paket in jedem Projekt installiert werden, in dem sie ausgeführt werden sollen. Sie müssen nur von einem Entwickler zum Projekt hinzugefügt werden. Das Analyzerpaket stellt eine Projektabhängigkeit dar und wird auf den Computern aller Entwickler ausgeführt, sobald eine aktualisierte Projektmappe vorhanden ist.

Der .NET Framework Analyzer wird im NuGet-Paket [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) bereitgestellt. Dieses Paket stellt nur die spezifischen Analysetools für das .NET Framework bereit und umfasst auch Sicherheitsanalysetools. In den meisten Fällen werden Sie das NuGet-Paket [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) benötigen. Das aggregierte FxCopAnalyzers-Paket enthält alle Framework-Analysetools im Framework.Analyzers-Paket sowie die folgenden Analysetools:

- [Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Bietet allgemeine Empfehlungen und Empfehlungen für .NET Standard-APIs.
- [Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Bietet Analysetools speziell für .NET Core-APIs.
- [Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Bietet Empfehlungen für Text in Form von Code, einschließlich Kommentaren.

Um das Paket zu installieren, klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie „Abhängigkeiten verwalten“ aus.
Suchen Sie im NuGet-Explorer nach „NetFramework Analyzer“ oder nach „Fx Cop Analyzer“, wenn Sie Letzteren bevorzugen. Installieren Sie die letzte als stabil bekannte Version in allen Projekten Ihrer Projektmappe.

## <a name="using-the-net-framework-analyzer"></a>Verwenden des .NET Framework Analyzers

Sobald das NuGet-Paket installiert ist, erstellen Sie Ihre Projektmappe. Das Analysetool meldet alle Probleme, die es in Ihrer Codebasis ermittelt. Die Probleme werden in Form von Warnungen im Visual Studio-Fenster „Fehlerliste“ gemeldet, wie in der folgenden Abbildung veranschaulicht:

![Probleme, die vom Framework Analyzer gemeldet werden.](./media/framework-analyzers-2.png)

Während Sie Code schreiben, werden potenzielle Probleme mit Wellenlinien unter dem fraglichen Codesegment angezeigt.
Wenn Sie mit der Maus auf ein potenzielles Problem zeigen, werden Details zum Problem sowie Vorschläge für eine mögliche Behebung angezeigt, wie in der folgenden Abbildung veranschaulicht:

![Interaktiver Bericht zu Fehlern, die vom Framework-Analysetool gefunden wurden](./media/framework-analyzers-1.png)

Die Analysetools untersuchen den Code in Ihrer Projektmappe und liefern Ihnen eine Liste mit Warnungen zu jedem dieser möglichen Probleme:

### <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Typen sollten bestimmte Basistypen nicht erweitern.

Es gibt einige wenige Typen in .NET Framework, aus denen Sie nicht direkt ableiten sollten. 

**Kategorie**: Entwurf

**Schweregrad**: Warnung

Zusätzliche Informationen: [CA:1058: Typen sollten bestimmte Basistypen nicht erweitern](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a>CA2153: Keine Corrupted State Exceptions abfangen

Durch das Abfangen von Corrupted State Exceptions könnten Fehler (z.B. Zugriffsverletzungen) verschleiert werden, was zu einem inkonsistenten Ausführungsstatus führen oder es Angreifern erleichtern könnte, ein System zu gefährden. Fangen Sie stattdessen einen spezifischeren Satz von Ausnahmetypen ab, und behandeln Sie diese, oder lösen Sie die Ausnahme erneut aus.

**Kategorie**: Sicherheit

**Schweregrad**: Warnung

Zusätzliche Informationen: [## CA2153: Keine Corrupted State Exceptions abfangen](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)

### <a name="ca2229-implement-serialization-constructors"></a>CA2229: Serialisierungskonstruktoren implementieren.

Das Analysetool generiert diese Warnung, wenn Sie einen Typ erstellen, der die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementiert, aber den erforderlichen Serialisierungskonstruktor nicht definiert. Um einen Verstoß gegen diese Regel zu beheben, implementieren Sie den Serialisierungskonstruktor. Definieren Sie den Konstruktor bei einer versiegelten Klasse als privaten Konstruktor. Definieren Sie ihn andernfalls als geschützten Konstruktor. Der Serialisierungskonstruktor weist die folgende Signatur auf:

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

**Kategorie**: Verwendung

**Schweregrad**: Warnung

Zusätzliche Informationen: [CA2229: Serialisierungskonstruktoren implementieren](/visualstudio/code-quality/ca2229-implement-serialization-constructors)

### <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Alle nicht serialisierbaren Felder markieren.

Ein Instanzenfeld eines Typs, der nicht serialisierbar ist, ist in einem serialisierbaren Typ deklariert. Sie müssen dieses Feld explizit mit dem <xref:System.NonSerializedAttribute> markieren, um diese Warnung zu beheben.

**Kategorie**: Verwendung

**Schweregrad**: Warnung

Zusätzliche Informationen: [CA2235: Alle nicht serialisierbaren Felder markieren](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)

### <a name="ca2237-mark-iserializable-types-with-serializable"></a>CA2237: ISerializable-Typen als serialisierbar markieren

Damit Typen von der Common Language Runtime als serialisierbar erkannt werden, müssen sie mit dem <xref:System.SerializableAttribute>-Attribut markiert werden, auch wenn der Typ durch die Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle eine benutzerdefinierte Serialisierungsroutine verwendet.

**Kategorie**: Verwendung

**Schweregrad**: Warnung

Zusätzliche Informationen: [CA2237: ISerializable-Typen als serialisierbar markieren](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)

### <a name="ca3075-insecure-dtd-processing-in-xml"></a>CA3075: Unsichere DTD-Verarbeitung in XML

Wenn Sie unsichere <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> -Instanzen oder externe Entitätsquellen verweisen, kann der Parser unter Umständen nicht vertrauenswürdige Eingaben akzeptieren und Angreifern vertrauliche Informationen offenlegen.  

**Kategorie**: Sicherheit

**Schweregrad**: Warnung

Zusätzliche Informationen: [A3075: Unsichere DTD-Verarbeitung in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)

### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: Keine schwachen Kryptografiealgorithmen verwenden

Kryptografiealgorithmen verlieren im Lauf der Zeit an Stärke, da Angriffe immer ausgefeilter werden. Je nach Typ und Anwendung dieses Kryptografiealgorithmus kann eine weitere Verschlechterung der kryptografischen Stärke dazu führen, dass Angreifer verschlüsselte Nachrichten lesen und manipulieren, digitale Signaturen fälschen, Hashinhalte manipulieren oder auf andere Weise ein Kryptografiesystem gefährden, das auf diesem Algorithmus basiert. Verwenden Sie für die Verschlüsselung einen AES-Algorithmus (AES-256, AES-192 und AES-128 sind akzeptabel) mit einer Schlüssellänge von mindestens 128 Bits. Verwenden Sie für das Hashing eine Hashfunktion in der SHA-2-Familie, wie z.B. SHA-2 512, SHA-2 384 oder SHA-2 256.

**Kategorie**: Sicherheit

**Schweregrad**: Warnung

Zusätzliche Informationen: [CA5350: Keine schwachen Kryptografiealgorithmen verwenden](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351: Keine beschädigten kryptografischen Algorithmen verwenden

Es gibt einen Angriff, der es rechnerisch möglich macht, diesen Algorithmus zu durchbrechen. Dies ermöglicht es Angreifern, die kryptografischen Garantien zu durchbrechen, die der Algorithmus bereitstellen soll. Je nach Typ und Anwendung dieses Kryptografiealgorithmus kann dies dazu führen, dass Angreifer verschlüsselte Nachrichten lesen und manipulieren, digitale Signaturen fälschen, Hashinhalte manipulieren oder auf andere Weise ein Kryptografiesystem gefährden, das auf diesem Algorithmus basiert. Verwenden Sie für die Verschlüsselung einen AES-Algorithmus (AES-256, AES-192 und AES-128 sind akzeptabel) mit einer Schlüssellänge von mindestens 128 Bits. Verwenden Sie für das Hashing eine Hashfunktion in der SHA-2-Familie, wie z.B. SHA512, SHA384 oder SHA256. Verwenden Sie für digitale Signaturen RSA mit einer Schlüssellänge von mindestens 2048 Bits oder ECDSA mit einer Schlüssellänge von mindestens 256 Bits.

**Kategorie**: Sicherheit

**Schweregrad**: Warnung

Zusätzliche Informationen: [CA5351: Keine beschädigten kryptografischen Algorithmen verwenden](/visualstudio/code-quality/ca5351)
