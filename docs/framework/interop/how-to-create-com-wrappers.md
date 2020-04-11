---
title: 'Vorgehensweise: Erstellen von COM-Wrappern'
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
ms.openlocfilehash: 035d6439ec90426d7b68e05043ea8b6722f81d28
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121601"
---
# <a name="how-to-create-com-wrappers"></a>Vorgehensweise: Erstellen von COM-Wrappern

Sie können mit Visual Studio 2005-Features oder den .NET Framework-Tools „Tlbimp.exe“ und „Regasm.exe“ COM-Wrapper (Component Object Model) erstellen. Beide Methoden generieren zwei Typen von COM-Wrappern:

- Ein [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) aus einer Typbibliothek führt ein COM-Objekt in verwaltetem Code aus.

- Ein [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) mit den erforderlichen Registrierungseinstellungen führt ein verwaltetes Objekt in einer nativen Anwendung aus.

In Visual Studio 2005 können Sie den COM-Wrapper als Verweis zu Ihrem Projekt hinzufügen.

## <a name="wrap-com-objects-in-a-managed-application"></a>Umschließen von COM-Objekten in einer verwalteten Anwendung

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a>Erstellen eines durch die Laufzeit aufrufbaren Wrappers mit Visual Studio

1. Öffnen Sie das Projekt für Ihre verwaltete Anwendung.

2. Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.

3. Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**.

4. Klicken Sie im Dialogfeld „Verweis hinzufügen“ auf die Registerkarte **COM**, wählen Sie die Komponente aus, die Sie verwenden möchten, und klicken Sie auf **OK**.

     Beachten Sie, dass die COM-Komponente im **Projektmappen-Explorer** dem Projektordner „Verweise“ hinzugefügt wird.

Sie können jetzt Code schreiben, um auf das COM-Objekt zuzugreifen. Sie können mit der Objektdeklaration beginnen, zum Beispiel mit einer `Imports`-Anweisung für Visual Basic oder einer `Using`-Anweisung für C#.

> [!NOTE]
> Wenn Sie Microsoft Office-Komponenten programmieren möchten, installieren Sie zunächst die [Microsoft Office Primary Interop Assemblies Redistributable](https://www.microsoft.com/Download/details.aspx?id=3508).
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a>Erstellen eines Runtime Callable Wrappers mit .NET Framework-Tools  
  
- Führen Sie das [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md) aus.  
  
 Dieses Tool erstellt eine Assembly, die Laufzeitmetadaten für die Typen enthält, die in der ursprünglichen Typbibliothek definiert wurden.  
  
## <a name="wrap-managed-objects-in-a-native-application"></a>Umschließen von verwalteten Objekten in einer nativen Anwendung  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a>Erstellen eines COM Callable Wrappers mit Visual Studio  
  
1. Erstellen Sie ein Klassenbibliotheksprojekt für die verwaltete Klasse, die Sie in nativem Code ausführen möchten. Die Klasse muss einen parameterlosen Konstruktor haben.  
  
     Überprüfen Sie, ob Sie eine vollständige vierteilige Versionsnummer für die Assembly in der AssemblyInfo-Datei besitzen. Diese Zahl ist für die Versionszuweisung in der Windows-Registrierung erforderlich. Weitere Informationen über die Versionsummern finden Sie unter [Assemblyversionen](../../standard/assembly/versioning.md).  
  
2. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
3. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
4. Aktivieren Sie das Kontrollkästchen **Für COM-Interop registrieren**.  
  
 Wenn Sie das Projekt erstellen, wird die Assembly für COM-Interop automatisch registriert. Wenn Sie in Visual Studio 2005 eine native Anwendung erstellen, können Sie die Assembly verwenden, indem Sie im Menü **Projekt** auf **Verweis hinzufügen** klicken.  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a>Erstellen eines COM Callable Wrappers mit .NET Framework-Tools  
  
Führen Sie das Tool [Regasm.exe (Assembly Registration-Tool)](../tools/regasm-exe-assembly-registration-tool.md) aus.  
  
Dieses Tool liest die Metadaten in einer Assembly und fügt der Registrierung die notwendigen Einträge hinzu. Folglich können COM-Clients .NET Framework-Klassen transparent erstellen. Sie können die Assembly verwenden, als handle es sich um eine native COM-Klasse.  
  
Sie können Regasm.exe für eine Assembly in jedem beliebigen Verzeichnis ausführen und anschließend das [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) ausführen, um sie in den globalen Assemblycache zu verschieben. Beim Verschieben der Assembly werden die Registrierungseinträge für den Speicherort nicht ungültig, da der globale Assemblycache immer überprüft wird, wenn die Assembly nicht an einem anderen Speicherort gefunden wird.  
  
## <a name="see-also"></a>Siehe auch

- [Runtime Callable Wrapper (RCW)](../../standard/native-interop/runtime-callable-wrapper.md)
- [COM Callable Wrapper (CCW)](../../standard/native-interop/com-callable-wrapper.md)
