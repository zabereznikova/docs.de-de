---
title: "Aktivitätslokalisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f7746e2ffc61db6d7863e243396f6d1bba315150
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="activity-localization"></a>Aktivitätslokalisierung
Wenn Workflowanwendungen und -Komponenten in andere Kulturen und Sprachen lokalisiert werden können, sollten Ressourcenzeichenfolgen verwendet werden, damit nach der Lokalisierung keine erneute Kompilierung ausgeführt werden muss.  
  
## <a name="activity-localization"></a>Aktivitätslokalisierung  
 Wie bei allen Anwendungen, die lokalisiert (in verschiedenen Versionen für andere Sprachen und Kulturen veröffentlicht) werden müssen, sollten sämtliche Zeichenfolgen, die dem Benutzer angezeigt werden, nicht direkt in den Code aufgenommen, sondern stattdessen in einer Ressourcendatei gespeichert werden. Die Zeichenfolgen können dann über zugegriffen werden <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`. Wenn Sie eine Komponente entwickeln, die in mehreren Sprachen herausgegeben wird, sollten Sie für Aktivitätsvalidierungsmeldungen, benutzerdefinierte Überwachungsdaten, Ablaufverfolgungsmeldungen und Fehlermeldungen ebenfalls Ressourcenzeichenfolgen verwenden.  
  
 Die folgende Übung demonstriert, wie eine Ressourcendatei verwendet wird.  
  
#### <a name="using-resource-files-for-localized-strings"></a>Verwenden von Ressourcendateien für lokalisierte Zeichenfolgen  
  
1.  In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], mit der rechten Maustaste des Projekts in **Projektmappen-Explorer** , und wählen Sie **hinzufügen...** , **Neues Element...** .  
  
2.  Wählen Sie **Ressourcendatei** und nennen Sie die Datei den Namen ErrorResources.resx. Klicken Sie auf **Hinzufügen**.  
  
3.  Öffnen Sie die Ressourcendatei. Fügen Sie einen neuen Eintrag mit einer **Namen** ErrorString und ein **Wert** von "ist die Aktivität nicht gültig."  
  
4.  Fügen Sie der Klasse die folgenden `using`-Anweisungen hinzu.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  Erstellen Sie einen Ressourcen-Manager in Ihrem Projekt.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  Rufen Sie die Zeichenfolge aus dem Ressourcen-Manager dahin ab, wo es erforderlich ist.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie lokalisierte Zeichenfolgen in der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode verwendet werden.  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
