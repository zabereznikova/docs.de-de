---
title: 'Vorgehensweise: Erstellen einer Herausgeberrichtlinie'
description: Erfahren Sie, wie assemblyhersteller eine Herausgeber Richtlinien Datei mit einer aktualisierten Assembly in .NET erstellen können, um festzulegen, dass Anwendungen die neuere Version verwenden sollten.
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 23e9d8144ec5742e0371d566b7af59dc9dd30c9b
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105402"
---
# <a name="how-to-create-a-publisher-policy"></a>Vorgehensweise: Erstellen einer Herausgeberrichtlinie

Anbieter von Assemblys können angeben, dass Anwendungen eine neuere Version einer Assembly verwenden sollen, indem Sie eine Herausgeber Richtlinien Datei mit der aktualisierten Assembly einschließen. Die Herausgeber Richtlinien Datei gibt die Assemblyumleitung und die Code Basis Einstellungen an und verwendet das gleiche Format wie eine Anwendungs Konfigurationsdatei. Die Herausgeber Richtlinien Datei wird in eine Assembly kompiliert und in den globalen Assemblycache eingefügt.

Zum Erstellen einer Herausgeber Richtlinie sind drei Schritte erforderlich:

1. Erstellen Sie eine Herausgeber Richtlinien Datei.

2. Erstellen Sie eine Herausgeber Richtlinien-Assembly.

3. Fügen Sie die Herausgeber Richtlinien-Assembly dem globalen Assemblycache hinzu

Das Schema für die Herausgeber Richtlinie wird unter [umleiten](redirect-assembly-versions.md)von Assemblyversionen beschrieben. Das folgende Beispiel zeigt eine Herausgeber Richtlinien Datei, die eine Version von `myAssembly` zu einer anderen umleitet.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Informationen zum Angeben einer Codebasis finden Sie unter [angeben des Speicher Orts einer Assembly](specify-assembly-location.md).

## <a name="creating-the-publisher-policy-assembly"></a>Erstellen der Herausgeber Richtlinien-Assembly

Verwenden Sie den [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) , um die Herausgeber Richtlinien-Assembly zu erstellen.

#### <a name="to-create-a-publisher-policy-assembly"></a>So erstellen Sie eine Herausgeber Richtlinien-Assembly

Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

In diesem Befehl:

- Das- `publisherPolicyFile` Argument ist der Name der Herausgeber Richtlinien Datei.

- Das- `publisherPolicyAssemblyFile` Argument ist der Name der Herausgeber Richtlinienassembly, die sich aus diesem Befehl ergibt. Der Assemblydateiname muss das folgende Format aufweisen:

  "policy.majorNumber.minorNumber.mainAssemblyName.dll"

- Das- `keyPairFile` Argument ist der Name der Datei, die das Schlüsselpaar enthält. Sie müssen die Assembly-und Herausgeber richtlinienassembly mit demselben Schlüsselpaar signieren.

- Das- `processorArchitecture` Argument identifiziert die Plattform, auf die eine prozessorspezifische Assembly abzielt.

  > [!NOTE]
  > Die Möglichkeit, eine bestimmte Prozessorarchitektur als Ziel zu erreichen, ist ab .NET Framework 2,0 verfügbar.

Die Möglichkeit, eine bestimmte Prozessorarchitektur als Ziel zu erreichen, ist ab .NET Framework 2,0 verfügbar. Der folgende Befehl erstellt eine Herausgeber richtlinienassembly `policy.1.0.myAssembly` , die mit einer Herausgeber Richtlinien Datei namens erstellt `pub.config` wird, weist der Assembly einen starken Namen zu, indem das Schlüsselpaar in der `sgKey.snk` Datei verwendet wird, und gibt an, dass die Assembly die x86-Prozessor

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

Die Herausgeber richtlinienassembly muss der Prozessorarchitektur der Assembly entsprechen, auf die Sie angewendet wird. Wenn die Assembly also <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> den Wert hat <xref:System.Reflection.ProcessorArchitecture.MSIL> , muss die Herausgeber richtlinienassembly für diese Assembly mit erstellt werden `/platform:anycpu` . Sie müssen für jede prozessorspezifische Assembly eine separate Herausgeber richtlinienassembly bereitstellen.

Eine Folge dieser Regel besteht darin, dass Sie die Haupt-oder neben Komponente der Versionsnummer ändern müssen, damit Sie eine neue Herausgeber richtlinienassembly mit der richtigen Prozessorarchitektur bereitstellen können, um die Prozessorarchitektur für eine Assembly zu ändern. Die alte Herausgeber richtlinienassembly kann die Assembly nicht bedienen, wenn die Assembly über eine andere Prozessorarchitektur verfügt.

Eine weitere Konsequenz besteht darin, dass der Linker der Version 2,0 nicht verwendet werden kann, um eine Herausgeber richtlinienassembly für eine Assembly zu erstellen, die mit früheren Versionen der .NET Framework kompiliert wurde

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Hinzufügen der Herausgeber Richtlinien-Assembly zum globalen Assemblycache

Fügen Sie die Herausgeber richtlinienassembly mit dem [Global Assembly Cache-Tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) dem globalen Assemblycache hinzu.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>So fügen Sie die Herausgeber Richtlinien-Assembly dem globalen Assemblycache

Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

```console
gacutil /i publisherPolicyAssemblyFile
```

Der folgende Befehl fügt dem `policy.1.0.myAssembly.dll` globalen Assemblycache hinzu.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> Die Herausgeber richtlinienassembly kann nicht zum globalen Assemblycache hinzugefügt werden, es sei denn, die ursprüngliche Herausgeber Richtlinien Datei `/link` befindet sich im selben Verzeichnis wie die Assembly.

## <a name="see-also"></a>Siehe auch

- [Programmieren mit Assemblys](../../standard/assembly/index.md)
- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps mithilfe von Konfigurationsdateien](index.md)
- [Schema für Laufzeiteinstellungen](./file-schema/runtime/index.md)
- [Konfigurationsdateischema](./file-schema/index.md)
- [Umleiten von Assemblyversionen](redirect-assembly-versions.md)
