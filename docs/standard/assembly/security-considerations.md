---
title: Überlegungen zur Assemblysicherheit
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], security
- signcodes
- names [.NET Framework], assemblies
- strong-named assemblies, security considerations
- signing assemblies
- assemblies [.NET Framework], signing
- granting permissions, assemblies
- assemblies [.NET Framework], strong-named
- names [.NET Framework], strong names
- permissions [.NET Framework], assemblies
- security [.NET Framework], assemblies
- integrity with assemblies
ms.assetid: 1b5439c1-f3d5-4529-bd69-01814703d067
ms.openlocfilehash: 2cd12ea49723bdac734c6847d337d945a5cfcb5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138619"
---
# <a name="assembly-security-considerations"></a>Überlegungen zur Assemblysicherheit
<a name="top"></a> Beim Erstellen einer Assembly können Sie eine Reihe von Berechtigungen angeben, die erforderlich sind, um die Assembly auszuführen. Das Erteilen bestimmter Berechtigungen für eine Assembly beruht auf Beweisen.  
  
 Beweise werden auf zwei unterschiedliche Arten verwendet:  
  
- Die Eingabebeweise werden mit den vom Ladeprogramm erfassten Beweisen zusammengeführt, um einen endgültigen Beweissatz zu erstellen. Dieser wird für die Richtlinienauflösung verwendet. Diese Semantik wird von den Methoden **Assembly.Load**, **Assembly.LoadFrom** und **Activator.CreateInstance** verwendet.  
  
- Die Eingabebeweise werden unverändert als endgültiger Beweissatz für die Richtlinienauflösung verwendet. Diese Semantik wird von den Methoden **Assembly.Load(byte[])** und **AppDomain.DefineDynamicAssembly()** verwendet.  
  
  Optionale Berechtigungen können über die [Sicherheitsrichtlinien](../../framework/misc/code-access-security-basics.md) erteilt werden, die auf dem Computer festgelegt sind, auf dem die Assembly ausgeführt wird. Wenn der Code alle potenziellen Sicherheitsausnahmen behandeln soll, können Sie eines der folgenden Verfahren durchführen:  
  
- Sie fügen eine Berechtigungsanforderung für alle Berechtigungen ein, über die der Code verfügen muss, und behandeln zuerst den Ladezeitfehler, der auftritt, wenn die Berechtigungen nicht erteilt werden.  
  
- Sie fordern die vom Code eventuell benötigten Berechtigungen nicht mit Berechtigungsanforderungen an, bereiten jedoch die Behandlung von Sicherheitsausnahmen für den Fall vor, dass keine Berechtigungen erteilt werden.  
  
  > [!NOTE]
  > Sicherheit ist ein komplexer Themenbereich, und Sie können aus einer Vielzahl von Optionen auswählen. Weitere Informationen finden Sie unter [Schlüsselbegriffe der Sicherheit](../../standard/security/key-security-concepts.md).  
  
 Zur Ladezeit wird der Beweis der Assembly als Eingabe für die Sicherheitsrichtlinie verwendet. Die Sicherheitsrichtlinie wird durch den Administrator der Organisation und des Computers sowie durch die Benutzerrichtlinieneinstellungen eingerichtet und bestimmt den Satz von Berechtigungen, der sämtlichem verwalteten Code beim Ausführen erteilt wird. Die Sicherheitsrichtlinie kann für den Herausgeber der Assembly eingerichtet werden (dazu ist eine mit dem Signaturtool generierte Signatur erforderlich). Sie kann außerdem für die Website und die Zone (als solche in Internet Explorer bezeichnet), von der die Assembly heruntergeladen wurde, oder für den starken Namen der Assembly eingerichtet werden. Der für einen Computer zuständige Administrator kann z. B. eine Sicherheitsrichtlinie einrichten, über die Code, der von einer Website heruntergeladen und von einer bestimmten Softwarefirma signiert ist, auf die Datenbank auf einem Computer zugreifen kann. Die Sicherheitsrichtlinie lässt es aber nicht zu, dass auf die Festplatte dieses Computers geschrieben wird.  
  
## <a name="strong-named-assemblies-and-signing-tools"></a>Assemblys mit starkem Namen und Signierungstools  

 > [!WARNING]
 > Verlassen Sie sich für die Sicherheit nicht auf starke Namen. Diese Namen bieten lediglich eine eindeutige Identität.

 Sie können eine Assembly auf zwei unterschiedliche, sich jedoch gegenseitig ergänzende Arten signieren: mit einem starken Namen oder mithilfe von [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md). Beim Signieren einer Assembly mit einem starken Namen wird der Datei, die das Assemblymanifest enthält, eine Verschlüsselung mit einem öffentlichen Schlüssel hinzugefügt. Das Signieren mit starkem Namen gewährleistet die Eindeutigkeit der Namen, verhindert das Vortäuschen von Namen (Spoofing) und stellt Aufrufern beim Auflösen eines Verweises eine Identität bereit.  
  
 Mit einem starken Namen ist keine Vertrauensebene verknüpft. Daher ist die Verwendung von [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) wichtig. Beim Einsatz der beiden Signaturtools müssen Herausgeber ihre Identität gegenüber einer dritten Stelle beweisen und ein Zertifikat anfordern. Dieses Zertifikat wird dann in die Datei eingebettet und kann von einem Administrator bei der Entscheidung verwendet werden, ob die Authentizität von Code vertrauenswürdig ist.  
  
 Sie können einer Assembly sowohl einen starken Namen als auch eine mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) erstellte digitale Signatur zuordnen, können diese Optionen jedoch auch einzeln verwenden. Mit den beiden Signaturtools kann immer nur jeweils eine Datei signiert werden. Bei einer Mehrfachdateiassembly signieren Sie die Datei, die das Assemblymanifest enthält. Ein starker Name ist in der Datei mit dem Assemblymanifest gespeichert, eine mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) erstellte Signatur wird jedoch in einem reservierten Slot der PE-Datei (Portable Executable, übertragbare ausführbare Datei) mit dem Assemblymanifest gespeichert. Eine Assembly kann mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) signiert werden (mit oder ohne starken Namen), wenn bereits eine Vertrauenshierarchie auf der Basis von mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) generierten Signaturen vorhanden ist oder die Richtlinie nur den Teil mit dem Schlüssel verwendet und keine Kette von Vertrauensstellungen überprüft.  
  
> [!NOTE]
> Wenn für eine Assembly sowohl ein starker Name als auch eine Signaturtool-Signatur erforderlich ist, muss zuerst der starke Name zugeordnet werden.  
  
 Die Common Language Runtime führt darüber hinaus eine Hashüberprüfung durch: Das Assemblymanifest enthält eine Liste aller Dateien, aus denen die Assembly besteht, einschließlich eines Hash für jede Datei, wie sie beim Erstellen des Manifests vorlag. Beim Laden der einzelnen Dateien werden die Inhalte gehasht und mit dem letzten Hashwert verglichen, der im Manifest gespeichert ist. Wenn die zwei Hashs nicht übereinstimmen, wird die Assembly nicht geladen.  
  
 Da starke Namen und das Signieren mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) die Integrität garantieren, können Sie der Sicherheitsrichtlinie für den Codezugriff diese beiden Formen von Assemblybeweisen zugrunde legen. Starke Namen und das Signieren mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md) garantieren die Integrität durch digitale Signaturen und Zertifikate. Alle genannten Technologien (Hashüberprüfung, starke Namen und das Signieren mit [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md)) gewährleisten gemeinsam, dass die Assembly in keiner Weise geändert werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys mit starken Namen](strong-named.md)
- [Assemblys in .NET](index.md)
- [SignTool.exe (Signaturtool)](../../framework/tools/signtool-exe.md)
