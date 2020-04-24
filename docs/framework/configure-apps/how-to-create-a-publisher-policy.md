---
title: 'Vorgehensweise: Erstellen einer Herausgeberrichtlinie'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646061"
---
# <a name="how-to-create-a-publisher-policy"></a>Vorgehensweise: Erstellen einer Herausgeberrichtlinie

Anbieter von Assemblys können angeben, dass Anwendungen eine neuere Version einer Assembly verwenden sollten, indem sie eine Herausgeberrichtliniendatei in die aktualisierte Assembly einschließen. Die Herausgeberrichtliniendatei gibt Assemblyumleitungs- und Codebasiseinstellungen an und verwendet das gleiche Format wie eine Anwendungskonfigurationsdatei. Die Herausgeberrichtliniendatei wird in eine Assembly kompiliert und im globalen Assemblycache abgelegt.

Beim Erstellen einer Herausgeberrichtlinie sind drei Schritte erforderlich:

1. Erstellen Sie eine Publisher-Richtliniendatei.

2. Erstellen Sie eine Herausgeberrichtlinienassembly.

3. Fügen Sie die Herausgeberrichtlinienassembly dem globalen Assemblycache hinzu.

Das Schema für die Herausgeberrichtlinie wird unter [Umleiten von Assemblyversionen](redirect-assembly-versions.md)beschrieben. Das folgende Beispiel zeigt eine Herausgeberrichtliniendatei, `myAssembly` die eine Version von einer anderen umleitet.

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

Informationen zum Angeben einer Codebasis finden Sie unter [Angeben des Speicherorts einer Assembly](specify-assembly-location.md).

## <a name="creating-the-publisher-policy-assembly"></a>Erstellen der Publisher-Richtlinienassembly

Verwenden Sie den [Assemblylinker (Al.exe),](../tools/al-exe-assembly-linker.md) um die Herausgeberrichtlinienassembly zu erstellen.

#### <a name="to-create-a-publisher-policy-assembly"></a>So erstellen Sie eine Herausgeberrichtlinienassembly

Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

In diesem Befehl:

- Das `publisherPolicyFile` Argument ist der Name der Herausgeberrichtliniendatei.

- Das `publisherPolicyAssemblyFile` Argument ist der Name der Herausgeberrichtlinienassembly, die sich aus diesem Befehl ergibt. Der Assemblydateiname muss dem Folgenden folgen:

  'policy.majorNumber.minorNumber.mainAssemblyName.dll'

- Das `keyPairFile` Argument ist der Name der Datei, die das Schlüsselpaar enthält. Sie müssen die Assembly- und Herausgeberrichtlinienassembly mit demselben Schlüsselpaar signieren.

- Das `processorArchitecture` Argument identifiziert die Plattform, auf die eine prozessorspezifische Assembly abzielt.

  > [!NOTE]
  > Die Möglichkeit, auf eine bestimmte Prozessorarchitektur zu zielen, ist ab .NET Framework 2.0 verfügbar.

Die Möglichkeit, auf eine bestimmte Prozessorarchitektur zu zielen, ist ab .NET Framework 2.0 verfügbar. Mit dem folgenden Befehl wird `policy.1.0.myAssembly` eine Herausgeberrichtlinienassembly `pub.config`erstellt, die aus einer Herausgeberrichtliniendatei namens `sgKey.snk` aufgerufen wird, der Assembly mithilfe des Schlüsselpaars in der Datei einen starken Namen zuweist und angibt, dass die Assembly auf die x86-Prozessorarchitektur abzielt.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

Die Herausgeberrichtlinienassembly muss mit der Prozessorarchitektur der Assembly übereinstimmen, auf die sie angewendet wird. Wenn Ihre Assembly den <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>von hat, muss daher die `/platform:anycpu`Herausgeberrichtlinienassembly für diese Assembly mit erstellt werden. Sie müssen für jede prozessorspezifische Assembly eine separate Herausgeberrichtlinienassembly bereitstellen.

Diese Regel hat zur Folge, dass Sie zum Ändern der Prozessorarchitektur für eine Assembly die Haupt- oder Nebenkomponente der Versionsnummer ändern müssen, damit Sie eine neue Herausgeberrichtlinienassembly mit der richtigen Prozessorarchitektur bereitstellen können. Die alte Herausgeberrichtlinienassembly kann Ihre Assembly nicht mehr bedienen, wenn die Assembly über eine andere Prozessorarchitektur verfügt.

Eine weitere Folge ist, dass der Linker version 2.0 nicht zum Erstellen einer Herausgeberrichtlinienassembly für eine Assembly verwendet werden kann, die mit früheren Versionen von .NET Framework kompiliert wurde, da er immer die Prozessorarchitektur angibt.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Hinzufügen der Publisher-Richtlinienassembly zum globalen Assemblycache

Verwenden Sie das [Werkzeug Globaler Assemblycache (Gacutil.exe),](../tools/gacutil-exe-gac-tool.md) um die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzuzufügen.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>So fügen Sie die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzu

Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

```console
gacutil /i publisherPolicyAssemblyFile
```

Der folgende `policy.1.0.myAssembly.dll` Befehl wird dem globalen Assemblycache hinzugefügt.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> Die Herausgeberrichtlinienassembly kann dem globalen Assemblycache nur hinzugefügt werden, `/link` wenn sich die im Argument angegebene ursprüngliche Herausgeberrichtliniendatei im selben Verzeichnis wie die Assembly befindet.

## <a name="see-also"></a>Siehe auch

- [Programmieren mit Assemblys](../../standard/assembly/index.md)
- [So sucht die Laufzeit Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps mithilfe von Konfigurationsdateien](index.md)
- [Laufzeiteinstellungsschema](./file-schema/runtime/index.md)
- [Konfigurationsdateischema](./file-schema/index.md)
- [Umleiten von Assemblyversionen](redirect-assembly-versions.md)
