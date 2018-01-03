---
title: Registrieren von Assemblys mit COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1473fa07b57dcd19ea192db6cdb0a395f119b159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="registering-assemblies-with-com"></a>Registrieren von Assemblys mit COM
Sie können ein Befehlszeilentool namens [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) ausführen, um eine Assembly für die Verwendung mit COM zu registrieren bzw. eine bestehende Registrierung aufzuheben. Regasm.exe fügt der Systemregistrierung Informationen über die Klasse hinzu, damit COM-Clients die .NET Framework-Klasse transparent nutzen können. Die Klasse <xref:System.Runtime.InteropServices.RegistrationServices> stellt gleichwertige Funktionen bereit.  
  
 Eine verwaltete Komponente muss in der Windows-Registrierung registriert sein, damit sie von einem COM-Client aktiviert werden kann. Die folgende Tabelle zeigt die Schlüssel, die Regasm.exe der Windows-Registrierung in der Regel hinzufügt. (000000 steht hier für den tatsächlichen GUID-WERT.)  
  
|GUID|Beschreibung|Registrierungsschlüssel|  
|----------|-----------------|------------------|  
|CLSID|Klassen-ID|HKEY_CLASSES_ROOT\CLSID\\{000…000}|  
|IID|Schnittstellen-ID|HKEY_CLASSES_ROOT\Interface\\{000…000}|  
|LIBID|Bibliothek-ID|HKEY_CLASSES_ROOT\TypeLib\\{000... 000}|  
|ProgID|Programmatischer Bezeichner|HKEY_CLASSES_ROOT\000... 000|  
  
 Unter dem Schlüssel HKCR\CLSID\\{0000…0000} wird der Standardwert auf die ProgID der Klasse festgelegt, und zwei neue benannte Werte werden hinzugefügt, „Class“ und „Assembly“. Die Common Language Runtime liest den Wert „Assembly“ aus der Registrierung aus und übergibt ihn an den Assemblyresolver der Runtime. Der Assemblyresolver versucht, die Assembly anhand von Assemblyinformationen zu lokalisieren, z.B. Name und Versionsnummer. Damit der Assemblyresolver eine Assembly lokalisieren kann, muss sie sich an einem der folgenden Speicherorte befinden:  
  
-   Im globalen Assemblycache (die Assembly muss einen starken Namen haben)  
  
-   Im Anwendungsverzeichnis. Auf aus einem Anwendungspfad geladene Assemblies kann nur über diese Anwendung zugegriffen werden.  
  
-   Entlang eines Dateipfads, der in Regasm.exe mit der Option **/codebase** angegeben wurde.  
  
 Regasm.exe erstellt auch unter dem Schlüssel HKCR\CLSID\\{0000…0000} den Schlüssel InProcServer32. Als Standardwert für den Schlüssel ist der Name der DLL festgelegt, die die Common Language Runtime initialisiert (Mscoree.dll).  
  
## <a name="examining-registry-entries"></a>Untersuchen von Registrierungseinträgen  
 Das COM-Interop stellt eine standardmäßige Klassenfactoryimplementierung zum Erstellen einer Instanz einer beliebigen .NET Framework-Klasse bereit. Clients können für die verwaltete DLL **DllGetClassObject** aufrufen, um eine Klassenfactory zu erhalten und Objekte zu erstellen. Dies funktioniert genau wie bei jeder anderen COM-Komponente auch.  
  
 Für den Unterschlüssel `InprocServer32` wird statt einer traditionellen Bibliothek der COM-Typen ein Verweis auf die Datei „Mscoree.dll“ angezeigt. So wird angegeben, dass die Common Language Runtime das verwaltete Objekt erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Gewusst wie: Verweisen auf .NET-Typen in COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)  
 [Aufrufen eines.](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [Deploying an Application for COM Access (Bereitstellen einer Anwendung für COM-Zugriff)](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
