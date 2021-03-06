---
title: "Mitigação: normalização do caminho"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e30099e315f88bd051dca2e1f6c83d1bccc49569
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-normalization"></a>Mitigação: normalização do caminho
Começando com os aplicativos direcionados ao [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a normalização do caminho no .NET Framework foi alterada.  
  
## <a name="what-is-path-normalization"></a>O que é normalização do caminho?  
 Normalizar um caminho envolve modificar a cadeia de caracteres que identifica um caminho ou arquivo para que ele esteja em conformidade com um caminho válido no sistema operacional de destino. Normalmente, a normalização envolve:  
  
-   Padronização de separadores de diretório e componente.  
  
-   Aplicação do diretório atual a um caminho relativo.  
  
-   Avaliação do diretório relativo (`.`) ou do diretório pai (`..`) em um caminho.  
  
-   Remoção de determinados caracteres.  
  
## <a name="the-changes"></a>As alterações  
 Começando com os aplicativos direcionados ao [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a normalização do caminho foi alterada nos seguintes aspectos:  
  
-   O tempo de execução atende à função [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) do sistema operacional para normalizar caminhos.  
  
-   A normalização não envolve mais a remoção do fim dos segmentos do diretório (como um espaço no fim do nome de um diretório).  
  
-   Suporte à sintaxe do caminho do dispositivo em confiança total, incluindo `\\.\` e, para APIs de E/S de arquivo em mscorlib.dll, `\\?\`.  
  
-   O tempo de execução não valida caminhos de sintaxe do dispositivo.  
  
-   Há suporte ao uso da sintaxe de dispositivo para acessar fluxos de dados alternados.  
  
## <a name="impact"></a>Impacto  
 Para os aplicativos direcionados ao [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ou posteriores, essas alterações estão ativadas por padrão. Elas devem melhorar o desempenho e ao mesmo tempo permitir que os métodos acessem caminhos anteriormente inacessíveis.  
  
 Os aplicativos direcionados ao [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versões anteriores, mas que são executados no [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ou posteriores, não são afetados por essa alteração.  
  
## <a name="mitigation"></a>Redução  
 Os aplicativos direcionados ao [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ou posteriores podem recusar essa alteração e usar a normalização herdada adicionando o seguinte à seção [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) do arquivo de configuração de aplicativo:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 Os aplicativos direcionados ao [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ou anteriores, mas que são executados no [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ou posteriores, podem habilitar essas alterações para normalização do caminho adicionando a seguinte linha à seção [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) do arquivo de configuração de aplicativo:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Alterações de redirecionamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

