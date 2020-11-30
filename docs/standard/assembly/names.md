---
title: Assemblynamen
description: Erfahren Sie mehr über .NET-Assemblynamen und ihre Auswirkung auf den Assemblybereich und die Verwendung durch eine Anwendung sowie über die FullName-Eigenschaft.
ms.date: 08/19/2019
helpviewer_keywords:
- names [.NET], assemblies
- assemblies [.NET], names
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
ms.openlocfilehash: 9aa94b4ee54c0a663c9f38392d37369af9f27e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731448"
---
# <a name="assembly-names"></a>Assemblynamen

Der Name einer Assembly wird in Metadaten gespeichert und wirkt sich erheblich auf den Geltungsbereich einer Assembly aus. Zudem hat er Einfluss darauf, wie die Assembly von einer Anwendung verwendet wird. Eine Assembly mit starkem Namen hat einen vollqualifizierten Namen, der den Namen, die Kultur, den öffentlichen Schlüssel, die Versionsnummer und optional die Prozessorarchitektur der Assembly enthält. Verwenden Sie die <xref:System.Reflection.Assembly.FullName%2A>-Eigenschaft, um den vollqualifizierten Namen, häufig als Anzeigename bezeichnet, für geladene Assemblys abzurufen.

Die Runtime verwendet die Information zum Namen, um nach der Assembly zu suchen und sie von anderen Assemblys mit dem gleichen Namen zu unterscheiden. Eine Assembly mit dem starken Namen `myTypes` könnte z.B. folgenden vollqualifizierten Namen haben:

```
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil
```

In diesem Beispiel gibt der vollqualifizierte Name an, dass die Assembly `myTypes` einen starken Namen mit einem öffentlichen Schlüsseltoken hat, den Kulturwert für Englisch (USA) und die Versionsnummer 1.0.1234.0. Die Prozessorarchitektur ist `msil`. Das heißt, dass eine JIT-Kompilierung (Just-In-Time) in 32-Bit- oder 64-Bit-Code durchgeführt wird, je nach Betriebssystem und Prozessor.

> [!TIP]
> Die `ProcessorArchitecture`-Information ermöglicht prozessorspezifische Versionen von Assemblys. Sie können Versionen einer Assembly erstellen, deren Identität sich nur in der Prozessorarchitektur unterschiedet, z.B. prozessorspezifische 32-Bit- und 64-Bit-Versionen. Die Prozessorarchitektur ist für starke Namen nicht unbedingt erforderlich. Weitere Informationen finden Sie unter <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=nameWithType>.

 Code, der Typen in einer Assembly anfordert, muss einen vollqualifizierten Assemblynamen verwenden. Dies wird als vollqualifizierte Bindung bezeichnet. Die Teilbindung, die nur einen Assemblynamen angibt, ist nicht zulässig, wenn auf Assemblys im .NET Framework verwiesen wird.

 Alles Assemblyverweise auf Assemblys, aus denen das .NET Framework besteht, müssen auch den vollqualifizierten Namen der Assembly enthalten. Der Verweis auf die System.Data-Assembly von .NET Framework für Version 1.0 würde beispielsweise Folgendes enthalten:

```
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089
```

Die Version entspricht den Versionsnummern aller Assemblys des .NET Framework, die mit .NET Framework Version 1.0 geliefert wurden. Der Kulturwert von Assemblys von .NET Framework ist immer neutral, und der öffentliche Schlüssel entspricht dem im oben stehenden Beispiel gezeigten Schlüssel.

 Um z.B. einen Assemblyverweis in eine Konfigurationsdatei einzufügen, um einen Ablaufverfolgungslistener einzurichten, beziehen Sie den vollqualifizierten der Systemassembly von .NET Framework mit ein:

```xml
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />
```

> [!NOTE]
> Die Runtime beachtet bei Assemblynamen keine Groß- und Kleinschreibung, wenn sie diese an Assemblys bindet. Die im Assemblynamen verwendete Schreibweise wird aber beibehalten. Mehrere Funktionen im Windows SDK unterscheiden bei Assemblynamen zwischen Groß- und Kleinschreibung. Die besten Ergebnisse erhalten Sie, wenn Sie bei Assemblynamen Groß- und Kleinschreibung beachten.

## <a name="name-application-components"></a>Benennen von Anwendungskomponenten

 Die Runtime achtet nicht auf den Dateinamen, wenn sie die Identität einer Assembly bestimmt. Die Assemblyidentität, die aus dem Assemblynamen, deren Version, Kultur und starkem Namen besteht, muss für die Runtime eindeutig sein.

 Wenn Sie z. B. über eine Assembly mit dem Namen *myAssembly.exe* verfügen, die auf eine Assembly mit dem Namen *myAssembly.dll* verweist, wird die Bindung korrekt durchgeführt, wenn Sie *myAssembly.exe* ausführen. Wenn allerdings eine andere Anwendung *myAssembly.exe* mit der <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType>-Methode ausführt, erkennt die Runtime, dass `myAssembly` bereits geladen wurde, wenn *myAssembly.exe* eine Bindung zu `myAssembly` anfordert. In diesem Fall wird *myAssembly.dll* nicht geladen. Da *myAssembly.exe* den angeforderten Typ nicht enthält, wird eine <xref:System.TypeLoadException> ausgelöst.

 Um dieses Problem zu vermeiden, achten Sie darauf, dass die Assemblys, aus denen Ihre Anwendung besteht, nicht denselben Assemblynamen haben. Alternativ können Sie Assemblys mit dem gleichen Namen auch in unterschiedliche Verzeichnisse platzieren.

> [!NOTE]
> Wenn Sie im .NET Framework eine Assembly mit starkem Namen in den globalen Assemblycache einfügen, muss der Dateiname der Assembly mit dem Assemblynamen übereinstimmen. Davon ausgenommen sind Erweiterungen des Dateinamens wie *EXE* oder *DLL*. Wenn der Dateiname einer Assembly z. B. *myAssembly.dll* ist, muss der Assemblyname `myAssembly` sein. Private Assemblys, die nur im Stammanwendungsverzeichnis bereitgestellt wurden, können einen Assemblynamen haben, der sich vom Dateinamen unterscheidet.

## <a name="see-also"></a>Siehe auch

- [How to: Bestimmen des vollqualifizierten Namens einer Assembly](find-fully-qualified-name.md)
- [Erstellen von Assemblys](create.md)
- [Assemblys mit starken Namen](strong-named.md)
- [Globaler Assemblycache](../../framework/app-domains/gac.md)
- [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md)
