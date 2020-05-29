---
title: 'Vorgehensweise: Erstellen eines Schlüsselpaars aus öffentlichem und privatem Schlüssel'
description: Erfahren Sie, wie Sie ein öffentliches/privates kryptografisches Schlüsselpaar erstellen, mit dem während der Kompilierung eine Assembly mit starkem Namen erstellt wird.
ms.date: 08/20/2019
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 675871170e7fd4171f0fe09b04d1dbb8906beda4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378552"
---
# <a name="how-to-create-a-public-private-key-pair"></a>Vorgehensweise: Erstellen eines Schlüsselpaars aus öffentlichem und privatem Schlüssel

Um eine Assembly mit einem starken Namen zu signieren, benötigen Sie ein Schlüsselpaar, das aus einem öffentlichen und einem privaten Schlüssel besteht. Dieses kryptografische Schlüsselpaar wird während der Kompilierung zum Erstellen einer Assembly mit starkem Namen verwendet. Sie können ein Schlüsselpaar mit dem [Strong Name-Tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) erstellen. Schlüsselpaardateien haben in der Regel die Erweiterung *SNK*.

> [!NOTE]
> In Visual Studio umfassen die Projekteigenschaftenseiten für C# und Visual Basic die Registerkarte **Signierung**, auf der Sie auswählen können, ob vorhandene Schlüsseldateien verwendet oder neue Schlüsseldateien generiert werden sollen, ohne dass *Sn.exe* eingesetzt wird. In Visual C++ können Sie den Speicherort einer vorhandenen Schlüsseldatei auf der Eigenschaftenseite **Erweitert** im Abschnitt **Linker** des Abschnitts **Konfigurationseigenschaften** im Fenster **Eigenschaftenseiten** angeben. Die Verwendung des <xref:System.Reflection.AssemblyKeyFileAttribute>-Attributs zur Angabe von Schlüsseldateipaaren ist ab Visual Studio 2005 veraltet.

## <a name="create-a-key-pair"></a>Erstellen eines Schlüsselpaars

Geben Sie über eine Eingabeaufforderung den folgenden Befehl ein, um ein Schlüsselpaar zu erstellen:

**sn –k** \<*Dateiname*>

Bei diesem Befehl bezeichnet *Dateiname* den Namen der Ausgabedatei, die das Schlüsselpaar enthält.

Im folgenden Beispiel wird ein Schlüsselpaar mit dem Namen *sgKey.snk* erstellt.

```cmd
sn -k sgKey.snk
```

Wenn Sie eine Assembly verzögert signieren möchten und beide Schlüssel kontrollieren (was außer in Testszenarien kaum vorkommt), können Sie die folgenden Befehle verwenden, um ein Schlüsselpaar zu generieren, und daraus anschließend den öffentlichen Schlüssel in eine separate Datei extrahieren. Erstellen Sie zuerst das Schlüsselpaar:

```cmd
sn -k keypair.snk
```

Extrahieren Sie anschließend den öffentlichen Schlüssel aus dem Schlüsselpaar, und kopieren Sie ihn dann in eine separate Datei:

```cmd
sn -p keypair.snk public.snk
```

Nachdem Sie das Schlüsselpaar erstellt haben, müssen Sie die Datei so ablegen, dass die Tools zur Signierung mit starkem Namen Zugriff darauf haben.

Beim Signieren einer Assembly mit einem starken Namen sucht das [Assembly Linker-Tool (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) nach der Schlüsseldatei relativ zum aktuellen und zum Ausgabeverzeichnis. Wenn Sie einen Befehlszeilencompiler verwenden, können Sie den Schlüssel einfach in das aktuelle Verzeichnis kopieren, das die Codemodule enthält.

Wenn Sie eine frühere Version von Visual Studio verwenden, die in den Projekteigenschaften nicht die Registerkarte **Signierung** aufweist, sollten Sie die Schlüsseldatei im Projektverzeichnis speichern und das Dateiattribut wie folgt festlegen:

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a>Siehe auch

- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
