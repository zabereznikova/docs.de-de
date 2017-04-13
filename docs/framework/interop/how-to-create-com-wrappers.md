---
title: "How to: Create COM Wrappers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM,wrappers creating"
  - "COM,wrappers Visual Studio"
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Create COM Wrappers
Sie können COM\-Wrapper \(Component Object Model\) mit [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)]\-Funktionen oder den .NET Framework\-Tools Tlbimp.exe und Regasm.exe erstellen.  Beide Methoden generieren zwei Typen von COM\-Wrappern:  
  
-   Ein [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) aus einer Typbibliothek, um ein COM\-Objekt in verwaltetem Code auszuführen.  
  
-   Ein [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) mit den erforderlichen Registrierungseinstellungen, um ein verwaltetes Objekt in einer systemeigenen Anwendung auszuführen.  
  
 In [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] können Sie den COM\-Wrapper dem Projekt als Verweis hinzufügen.  
  
## Umschließen von COM\-Objekten in einer verwalteten Anwendung  
  
#### So erstellen Sie einen Runtime Callable Wrapper mit Visual Studio  
  
1.  Öffnen Sie das Projekt für die verwaltete Anwendung.  
  
2.  Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.  
  
3.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**.  
  
4.  Klicken Sie im Dialogfeld Verweis hinzufügen auf die Registerkarte **COM**, wählen Sie die gewünschte Komponente, und klicken Sie anschließend auf **OK**.  
  
     Beachten Sie, dass im **Projektmappen\-Explorer** dem Ordner Verweise des Projekts die COM\-Komponente hinzugefügt wird.  
  
 Sie können jetzt Code schreiben, um auf das COM\-Objekt zuzugreifen.  Sie können mit der Objektdeklaration beginnen, zum Beispiel mit einer `Imports`\-Anweisung für [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] oder einer `Using`\-Anweisung für [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].  
  
> [!NOTE]
>  Wenn Sie Microsoft Office\-Komponenten programmieren möchten, installieren Sie zunächst die primären Interop\-Assemblys \(PIAs\), die im Microsoft Download Center unter [Microsoft Office Primary Interop Assemblies](http://go.microsoft.com/fwlink/?LinkId=50479) verfügbar sind.  Wählen Sie in Schritt 4 die aktuelle Version der Objektbibliothek, die für das gewünschte Office\-Produkt zur Verfügung steht, z. B. **Microsoft Word 11.0\-Objektbibliothek**.  [](http://msdn.microsoft.com/de-de/c9d2a8b9-69df-4c0b-90ca-4d85bae063c4)  
  
#### So erstellen Sie einen Runtime Callable Wrapper mit .NET Framework\-Tools  
  
-   Führen Sie das [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)\-Tool aus.  
  
 Dieses Tool erstellt eine Assembly, die Laufzeitmetadaten für die Typen enthält, die in der ursprünglichen Typbibliothek definiert wurden.  
  
## Einbinden von verwalteten Objekten in einer systemeigenen Anwendung  
  
#### So erstellen Sie einen COM Callable Wrapper mit Visual Studio  
  
1.  Erstellen Sie ein Klassenbibliotheksprojekt für die verwaltete Klasse, die Sie in systemeigenem Code ausführen möchten.  Die Klasse muss über einen Standardkonstruktor verfügen.  
  
     Überprüfen Sie, ob Sie eine vollständige vierteilige Versionsnummer für die Assembly in der AssemblyInfo\-Datei besitzen.  Diese Zahl ist für die Versionszuweisung in der Windows\-Registrierung erforderlich.  Weitere Informationen zu Versionsnummern finden Sie unter [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md).  
  
2.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
3.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
4.  Aktivieren Sie das Kontrollkästchen **Für COM\-Interop registrieren**.  
  
 Wenn Sie das Projekt erstellen, wird die Assembly automatisch für COM\-Interop registriert.  Wenn Sie in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] eine systemeigene Anwendung erstellen, können Sie die Assembly verwenden, indem Sie im Menü **Projekt** auf **Verweis hinzufügen** klicken.  
  
#### So erstellen Sie einen COM Callable Wrapper mit .NET Framework\-Tools  
  
-   Führen Sie das [Regasm.exe \(Assembly Registration Tool\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)\-Tool aus.  
  
 Dieses Tool liest die Assemblymetadaten und fügt der Registrierung die notwendigen Einträge hinzu.  So können COM\-Clients .NET Framework\-Klassen transparent erstellen.  Sie können die Assembly wie eine systemeigene COM\-Klasse verwenden.  
  
 Sie können Regasm.exe für eine Assembly in jedem beliebigen Verzeichnis ausführen und anschließend das [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) ausführen, um sie in den globalen Assemblycache zu verschieben.  Beim Verschieben der Assembly werden die Registrierungseinträge für den Speicherort nicht ungültig, da der globale Assemblycache immer überprüft wird, wenn die Assembly an einem anderen Speicherort nicht gefunden wird.  
  
## Siehe auch  
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)