---
title: Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32-Namespaces
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 58c3a92067cd0be5db02231c5fc1a13b429a60a0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282238"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a>Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32-Namespaces (Visual Basic)

Obwohl `My.Computer.Registry` alle Ihre Basisanforderungen beim Programmieren der Registrierung abdecken soll, können Sie alternativ die Klassen <xref:Microsoft.Win32.Registry> und <xref:Microsoft.Win32.RegistryKey> im <xref:Microsoft.Win32>-Namespace von .NET verwenden.
  
## <a name="keys-in-the-registry-class"></a>Schlüssel in der Registry-Klasse  

 Die <xref:Microsoft.Win32.Registry>-Klasse stellt die Basisregistrierungsschlüssel bereit, die für den Zugriff auf Unterschlüssel und deren Werte verwendet werden können. Die Basisschlüssel selbst sind schreibgeschützt. In der folgenden Tabelle werden die sieben Schlüssel, die von der <xref:Microsoft.Win32.Registry>-Klasse verfügbar gemacht werden, aufgelistet und beschrieben.  
  
|**Key**|**Beschreibung**|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|Definiert die Typen von Dokumenten und die diesen Typen zugeordneten Eigenschaften.|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|Enthält Informationen zur Hardwarekonfiguration, die nicht spezifisch sind.|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|Enthält Informationen über die aktuellen Benutzereinstellungen, z.B. Umgebungsvariablen.|  
|<xref:Microsoft.Win32.Registry.DynData>|Enthält dynamische Registrierungsdaten, z.B. solche, die von virtuellen Gerätetreibern verwendet werden.|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|Enthält fünf Unterschlüssel (Hardware, SAM, Security, Software und System), die die Konfigurationsdaten für den lokalen Computer enthalten.|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|Enthält Informationen zur Leistung für Softwarekomponenten.|  
|<xref:Microsoft.Win32.Registry.Users>|Enthält Informationen zu den Standardeinstellungen für Benutzer.|  
  
> [!IMPORTANT]
> Es ist sicherer, Daten in den Schlüssel für den aktuellen Benutzer (<xref:Microsoft.Win32.Registry.CurrentUser>) statt in den Schlüssel für den lokalen Computer (<xref:Microsoft.Win32.Registry.LocalMachine>) zu schreiben. Eine Bedingung, die in der Regel als „squatting“ bezeichnet wird, tritt auf, wenn der Schlüssel, den Sie erstellen, zuvor von einem anderen, möglicherweise böswilligen Prozess erstellt wurde. Um dies zu vermeiden, verwenden Sie eine Methode, z.B. <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, die `Nothing` zurückgibt, wenn der Schlüssel nicht bereits vorhanden ist.  
  
## <a name="reading-a-value-from-the-registry"></a>Lesen eines Werts aus der Registrierung  

 Der folgende Code zeigt, wie eine Zeichenfolge aus HKEY_CURRENT_USER gelesen wird.  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 Der folgende Code liest, erhöht, und schreibt dann eine Zeichenfolge in HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [Try...Catch...Finally-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md)
- [Lesen aus der und Schreiben in die Registrierung](reading-from-and-writing-to-the-registry.md)
- [Sicherheit und die Registrierung](security-and-the-registry.md)
