---
title: "Aktivit&#228;tslokalisierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Aktivit&#228;tslokalisierung
Wenn Workflowanwendungen und \-Komponenten in andere Kulturen und Sprachen lokalisiert werden können, sollten Ressourcenzeichenfolgen verwendet werden, damit nach der Lokalisierung keine erneute Kompilierung ausgeführt werden muss.  
  
## Aktivitätslokalisierung  
 Wie bei allen Anwendungen, die lokalisiert \(in verschiedenen Versionen für andere Sprachen und Kulturen veröffentlicht\) werden müssen, sollten sämtliche Zeichenfolgen, die dem Benutzer angezeigt werden, nicht direkt in den Code aufgenommen, sondern stattdessen in einer Ressourcendatei gespeichert werden.Der Zugriff auf die Zeichenfolgen kann dann über die <xref:System.Environment.GetResourceString> erfolgen.Wenn Sie eine Komponente entwickeln, die in mehreren Sprachen herausgegeben wird, sollten Sie für Aktivitätsvalidierungsmeldungen, benutzerdefinierte Überwachungsdaten, Ablaufverfolgungsmeldungen und Fehlermeldungen ebenfalls Ressourcenzeichenfolgen verwenden.  
  
 Die folgende Übung demonstriert, wie eine Ressourcendatei verwendet wird.  
  
#### Verwenden von Ressourcendateien für lokalisierte Zeichenfolgen  
  
1.  Klicken Sie in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] mit der rechten Maustaste auf das Projekt im Projektmappen\-Explorer, und wählen Sie **Hinzufügen**, **Neues Element** aus.  
  
2.  Wählen Sie **Ressourcendatei** aus, und geben Sie der Datei den Namen ErrorResources.resx.Klicken Sie auf **Hinzufügen**.  
  
3.  Öffnen Sie die Ressourcendatei.Fügen Sie einen neuen Eintrag hinzu, und geben Sie unter **Name** ErrorString sowie unter **Wert** "Die Aktivität ist nicht gültig." ein.  
  
4.  Fügen Sie der Klasse die folgenden `using`\-Anweisungen hinzu.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
  
    ```  
  
5.  Erstellen Sie einen Ressourcen\-Manager in Ihrem Projekt.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
  
    ```  
  
6.  Rufen Sie die Zeichenfolge aus dem Ressourcen\-Manager dahin ab, wo es erforderlich ist.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
  
    ```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie lokalisierte Zeichenfolgen in der <xref:System.Activities.Activity.CacheMetadata%2A>\-Methode verwendet werden.  
  
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