---
title: "&#220;berlegungen zur Assemblysicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Sicherheit"
  - "Assemblys [.NET Framework], Signieren"
  - "Assemblys [.NET Framework], Mit starken Namen"
  - "Erteilen von Berechtigungen, Assemblys"
  - "Integrität mit Assemblys"
  - "Namen [.NET Framework], Assemblys"
  - "Namen [.NET Framework], Starke Namen"
  - "Berechtigungen [.NET Framework], Assemblys"
  - "Sicherheit [.NET Framework], Assemblys"
  - "Signaturcodes"
  - "Signieren von Assemblys"
  - "Assemblys mit starken Namen, Überlegungen zur Sicherheit"
ms.assetid: 1b5439c1-f3d5-4529-bd69-01814703d067
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;berlegungen zur Assemblysicherheit
Beim Erstellen einer Assembly können Sie eine Reihe von Berechtigungen angeben, die erforderlich sind, um die Assembly ausführen zu können.  Das Erteilen bestimmter Berechtigungen für eine Assembly beruht auf Beweisen.  
  
 Beweise werden auf zwei unterschiedliche Arten verwendet:  
  
-   Die Eingabebeweise werden mit den vom Ladeprogramm erfassten Beweisen zusammengeführt, um einen endgültigen Beweissatz zu erstellen. Dieser wird für die Richtlinienauflösung verwendet.  Diese Semantik wird von den Methoden **Assembly.Load**, **Assembly.LoadFrom** und **Activator.CreateInstance** verwendet.  
  
-   Die Eingabebeweise werden unverändert als endgültiger Beweissatz für die Richtlinienauflösung verwendet.  Diese Semantik wird von den Methoden **Assembly.Load\(byte\[\]\)** und **AppDomain.DefineDynamicAssembly\(\)** verwendet.  
  
 Optionale Berechtigungen können auch durch die [Sicherheitsrichtlinien](../../../docs/framework/misc/code-access-security-basics.md) des Computer erteilt werden, auf dem die Assembly ausgeführt wird.  Wenn der Code alle potenziellen Sicherheitsausnahmen behandeln soll, können Sie eines der folgenden Verfahren durchführen:  
  
-   Sie fügen eine Berechtigungsanforderung für alle Berechtigungen ein, über die der Code verfügen muss, und behandeln zuerst den Ladezeitfehler, der auftritt, wenn die Berechtigungen nicht erteilt werden.  
  
-   Sie fordern die vom Code eventuell benötigten Berechtigungen nicht mit Berechtigungsanforderungen an, bereiten jedoch die Behandlung von Sicherheitsausnahmen für den Fall vor, dass keine Berechtigungen erteilt werden.  
  
    > [!NOTE]
    >  Sicherheit ist ein komplexer Themenbereich, und Sie können aus einer Vielzahl von Optionen auswählen.  Weitere Informationen finden Sie unter [Schlüsselbegriffe der Sicherheit](../../../docs/standard/security/key-security-concepts.md).  
  
 Zur Ladezeit wird der Beweis der Assembly als Eingabe für die Sicherheitsrichtlinie verwendet.  Die Sicherheitsrichtlinie wird durch den Administrator der Organisation und des Computers sowie durch die Benutzerrichtlinieneinstellungen eingerichtet und bestimmt den Satz von Berechtigungen, der sämtlichem verwalteten Code beim Ausführen erteilt wird.  Die Sicherheitsrichtlinie kann für den Herausgeber der Assembly eingerichtet werden \(dazu ist eine mit dem Signaturtool generierte Signatur erforderlich\). Sie kann außerdem für die Website und die Zone \(als solche in Internet Explorer bezeichnet\), von der die Assembly heruntergeladen wurde, oder für den starken Namen der Assembly eingerichtet werden.  Der für einen Computer zuständige Administrator kann z. B. eine Sicherheitsrichtlinie einrichten, über die Code, der von einer Website heruntergeladen und von einer bestimmten Softwarefirma signiert ist, auf die Datenbank auf einem Computer zugreifen kann. Die Sicherheitsrichtlinie lässt es aber nicht zu, dass auf die Festplatte dieses Computers geschrieben wird.  
  
## Assemblys mit starkem Namen und Signaturtools  
 Sie können eine Assembly auf zwei unterschiedliche, sich jedoch gegenseitig ergänzende Arten signieren: mit einem starken Namen oder mithilfe der Tools [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) in .NET Framework, Version 1.0 und 1.1, bzw. [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) in neueren Versionen von .NET Framework.  Beim Signieren einer Assembly mit einem starken Namen wird der Datei, die das Assemblymanifest enthält, eine Verschlüsselung mit einem öffentlichen Schlüssel hinzugefügt.  Das Signieren mit starkem Namen gewährleistet die Eindeutigkeit der Namen, verhindert das Vortäuschen von Namen \(Spoofing\) und stellt Aufrufern beim Auflösen eines Verweises eine Identität bereit.  
  
 Mit einem starken Namen ist jedoch keine Vertrauensebene verknüpft, daher ist die Verwendung der Tools [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) wichtig.  Beim Einsatz der beiden Signaturtools müssen Herausgeber ihre Identität gegenüber einer dritten Stelle beweisen und ein Zertifikat anfordern.  Dieses Zertifikat wird dann in die Datei eingebettet und kann von einem Administrator bei der Entscheidung verwendet werden, ob die Authentizität von Code vertrauenswürdig ist.  
  
 Sie können einer Assembly sowohl einen starken Namen als auch eine mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) erstellte digitale Signatur zuordnen, können diese Optionen jedoch auch einzeln verwenden.  Mit den beiden Signaturtools kann immer nur jeweils eine Datei signiert werden. Bei einer Mehrfachdateiassembly signieren Sie die Datei, die das Assemblymanifest enthält.  Ein starker Name ist in der Datei mit dem Assemblymanifest gespeichert, eine mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) erstellte Signatur wird jedoch in einem reservierten Slot der PE\-Datei \(Portable Executable, übertragbare ausführbare Datei\) mit dem Assemblymanifest gespeichert.  Eine Assembly kann mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) signiert werden \(mit oder ohne einen starken Namen\), wenn bereits eine Vertrauenshierarchie auf der Basis von mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) generierten Signaturen vorhanden ist oder die Richtlinie nur den Teil mit dem Schlüssel verwendet und keine Kette von Vertrauensstellungen überprüft.  
  
> [!NOTE]
>  Wenn für eine Assembly sowohl ein starker Name als auch eine Signaturtool\-Signatur erforderlich ist, muss zuerst der starke Name zugeordnet werden.  
  
 Die Common Language Runtime führt darüber hinaus eine Hashüberprüfung durch: Das Assemblymanifest enthält eine Liste aller Dateien, aus denen die Assembly besteht, einschließlich eines Hash für jede Datei, wie sie beim Erstellen des Manifests vorlag.  Beim Laden der einzelnen Dateien werden die Inhalte gehasht und mit dem letzten Hashwert verglichen, der im Manifest gespeichert ist.  Wenn die zwei Hashs nicht übereinstimmen, wird die Assembly nicht geladen.  
  
 Da starke Namen und das Signieren mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) die Integrität garantieren, können Sie der Sicherheitsrichtlinie für den Codezugriff diese beiden Formen von Assemblybeweisen zugrunde legen.  Starke Namen und das Signieren mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md) garantieren die Integrität durch digitale Signaturen und Zertifikate.  Alle genannten Technologien \(Hashüberprüfung, starke Namen und das Signieren mit dem [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db) bzw. dem [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md)\) gewährleisten gemeinsam, dass die Assembly in keiner Weise geändert werden kann.  
  
## Siehe auch  
 [Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md)   
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md)   
 [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/de-de/2d299154-34ea-41ba-ad12-17075bb7e1db)