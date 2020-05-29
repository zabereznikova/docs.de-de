---
title: Verzögertes Signieren einer Assembly
description: In diesem Artikel wird die verzögerte oder partielle Signierung beschrieben, die in der PE-Datei Speicherplatz für die Signatur mit dem starken Namen reserviert, aber die tatsächliche Signatur verzögert.
ms.date: 08/19/2019
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 7b5c8c8463fdc573782fa457bf5671c72a7e25f7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378501"
---
# <a name="delay-sign-an-assembly"></a>Verzögertes Signieren einer Assembly

Organisationen können ein streng geheim gehaltenes Schlüsselpaar verwenden, auf das Entwickler nicht täglich zugreifen können. Der öffentliche Schlüssel stünde zur Verfügung, während der Zugriff auf den privaten Schlüssel nur einigen Wenigen erlaubt wäre. Beim Entwickeln von Assemblys mit starken Namen enthält jede Assembly, die auf die Zielassembly mit dem starken Namen verweist, das Token des öffentlichen Schlüssels, mit dem der starke Name der Zielassembly erzeugt wird. Aus diesem Grund muss der öffentliche Schlüssel während des Entwicklungsprozesses verfügbar sein.

Mit dem verzögerten Signieren oder dem Teilsignieren zur Buildzeit können Sie Speicherplatz in der portierbaren ausführbaren Datei (Portable Executable, PE) für die Signatur mit starkem Namen reservieren, das eigentliche Signieren aber auf einen späteren Zeitpunkt verschieben, i.d.R. unmittelbar vor der Weitergabe der Assembly.

So verzögern Sie das Signieren einer Assembly:

1. Holen Sie sich den öffentlichen Schlüssel des Schlüsselpaars von der Organisation, die letztendlich signieren wird. In der Regel liegt dieser Schlüssel in Form einer *SNK*-Datei vor, die mit dem vom Windows SDK bereitgestellten [Strong Name-Tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) erstellt werden kann.

2. Kommentieren Sie den Quellcode für die Assembly mit den zwei benutzerdefinierten Attribute aus <xref:System.Reflection>:

   - <xref:System.Reflection.AssemblyKeyFileAttribute>, das den Namen der Datei mit dem öffentlichen Schlüssel als Parameter an den Konstruktor übergibt

   - <xref:System.Reflection.AssemblyDelaySignAttribute>, das angibt, dass beim verzögerten Signieren **TRUE** als Parameter an den Konstruktor übergeben wird

   Zum Beispiel:

   ```cpp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")];
   [assembly:AssemblyDelaySignAttribute(true)];
   ```

   ```csharp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")]
   [assembly:AssemblyDelaySignAttribute(true)]
   ```

   ```vb
   <Assembly:AssemblyKeyFileAttribute("myKey.snk")>
   <Assembly:AssemblyDelaySignAttribute(True)>
   ```

3. Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und reserviert in der PE-Datei Speicherplatz für die vollständige Signatur mit starkem Namen. Der echte öffentliche Schlüssel muss während der Erstellung der Assembly gespeichert werden, damit andere Assemblys, die auf diese Assembly verweisen, den Schlüssel abrufen und in ihrem eigenen Assemblyverweis speichern können.

4. Da die Assembly über keine gültige Signatur mit starkem Namen verfügt, muss die Überprüfung der Signatur deaktiviert werden. Dies erreichen Sie mit der Option **–Vr** im Strong Name-Tool.

     Das folgende Beispiel deaktiviert die Überprüfung für eine Assembly namens *myAssembly.dll*.

   ```console
   sn –Vr myAssembly.dll
   ```

   Um die Überprüfung auf Plattformen wie Advanced RISC Machine-Mikroprozessoren (ARM) zu deaktivieren, auf denen das Strong Name-Tool nicht ausgeführt werden kann, erstellen Sie mit der Option **–Vk** eine Registrierungsdatei. Importieren Sie die Registrierungsdatei in die Registrierung des Computers, auf dem die Überprüfung deaktiviert werden soll. Im folgenden Beispiel wird eine Registrierungsdatei für `myAssembly.dll` erstellt.

   ```console
   sn –Vk myRegFile.reg myAssembly.dll
   ```

   Mit den Optionen **–Vr** oder **–Vk** lässt sich optional eine *SNK*-Datei zum Testen der Schlüsselsignatur einbeziehen.

   > [!WARNING]
   > Verlassen Sie sich für die Sicherheit nicht auf starke Namen. Diese Namen bieten lediglich eine eindeutige Identität.

   > [!NOTE]
   > Wenn Sie während der Entwicklung mit Visual Studio auf einem 64-Bit-Computer das verzögerte Signieren verwenden und eine Assembly für **Any CPU** (Beliebige CPU) kompilieren, müssen Sie die Option **-Vr** möglicherweise zweimal anwenden. In Visual Studio ist **Beliebige CPU** der Wert der Buildeigenschaft **Zielplattform**. Wenn Sie über die Befehlszeile kompilieren, ist dies der Standardwert. Um Ihre Anwendung über die Befehlszeile oder über den Datei-Explorer auszuführen, nutzen Sie die 64-Bit-Version von [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md), um die Option **-Vr** auf die Assembly anzuwenden. Wenn Sie die Assembly zur Entwurfszeit in Visual Studio laden möchten (z.B., wenn die Assembly Komponenten enthält, die von anderen Assemblys in Ihrer Anwendung verwendet werden), verwenden Sie die 32-Bit-Version des Strong Name-Tools. Dies ist notwendig, weil der Just-in-Time-Compiler (JIT) die Assembly in nativem 64-Bit-Code kompiliert, wenn die Assembly über die Befehlszeile ausgeführt wird, und in nativem 32-Bit-Code, wenn die Assembly in die Entwurfszeitumgebung geladen wird.

5. Zu einem späteren Zeitpunkt – in der Regel vor der Weitergabe der Assembly – übergeben Sie die Assembly an die Signierungsstelle Ihrer Organisation, um sie mit der Option **–R** und dem Strong Name-Tool mit starkem Namen signieren zu lassen.

   Im folgenden Beispiel wird eine Assembly namens *myAssembly.dll*, die das *sgKey.snk*-Schlüsselpaar enthält, mit starkem Namen signiert.

   ```console
   sn -R myAssembly.dll sgKey.snk
   ```

## <a name="see-also"></a>Siehe auch

- [Erstellen von Assemblys](create.md)
- [How to: Erstellen eines öffentlichen/privaten Schlüsselpaars](create-public-private-key-pair.md)
- [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md)
