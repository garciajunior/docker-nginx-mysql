# StatusPage Atlassian

Statuspage API para receber incidentes que possam ocorrer com o desenvolvimento de todos sos serviços da Smarkio.

  - https://altu.statuspage.io/

# Envio

  - Endpoint
 > 'https://api.statuspage.io/v1/pages/#{page_id}/components.json' 
  
O envio deve ser feito em formato JSON e método POST.

Os campos são obrigatórios, e devem estar no json:

$API_KEY : string - Key para acesso do cliente, deve ser obtida no ALTU.
$PAGE_ID : string -  Id da página criada 
$METRIC_ID : string - Metrica gerada  para passar informações a componentes especificos
$BASE_URI : string - 'https://api.statuspage.io/v1'; essa base é padrão do statuspage


### Json  para criar um Componente
```
{
  "api_key": string,
   "page_id": string,
   "metric_id": string,
   "base_uri":"https://api.statuspage.io/v1",
   "method" :"GET" ,"POST", "PUT" "PATCH" "DELETE",
   "data":{
      "component":{
         "name":"Problemas de implementação",
         "description":"Descrição do componente",
         "status":"operational",
         "only_show_if_degraded":true,
         "showcase":true
      }
    }
}
```

### Retorno Json
Todas as informações do componente criado.