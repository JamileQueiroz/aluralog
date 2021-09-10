# aluralog
Alura Challenge BI: Creating a logistics dashboard on Power BI


Logistics managers need to constantly monitor their department's metrics to make the best decisions specially due to the fact that the transportation market is facing some changes during the pandemic period.


Logistics metrics and their results are presented on a dashboard Power BI to help this sector in a fictional company named AluraLog.

Four databases are provided in CSV format:
orders - contains the record of all orders placed by customers. (in Portuguese: tabela pedidos)
products table - contains the registered products and their values.  (in Portuguese: tabela produtos)
Vehicles table - contains registered vehicles that transport the products  (in Portuguese: tabela veículos)
stock table - contains the inventory record of products by month  (in Portuguese: tabela estoque)

Logistics metrics:

Delivered Order: number of orders delivered within time limit (in Portuguese: Entregas dentro do prazo)
Delays: Number of orders delivered out of time limit (in Portuguese: Entregas atrasadas)
S2D - Ship to door: time it takes to pick and deliver orders
Incidents: Number of orders with delay and not delivered (in Portuguese: Ocorrências)
Available vehicles: Number of available vehicles to shipping (in Portuguese: Veículos disponíveis para entrega)

Revenues - (in Portuguese: Faturamento)
Product stock -  available product stock in warehouse (in Portuguese: Estoque disponível)



Formules on column tool Power BI:

Delivery status: 

Status de Entrega = IF([Data de entrega]<=[Data previsão],"Dentro do prazo”,"Atrasada")


Ship to door: 

S2D = [Data de entrega]-[Data da compra]


Incidents: 

Ocorrência = IF([Status de Entrega]="Atrasada",1,IF([Status do pedido]="Em trânsito”,1,0))

Product value: 

Valor Produto = LOOKUPVALUE('Tabela - Produtos'[Preço],'Tabela - Produtos'[ID Produto],[ID Produto])

Revenues:
Faturamento = [Quantidade]*[Valor Produto]



You can visualize these metrics to each State (Brazil), type of vehicle, and Product category for the past three years. 

Access to Dashboard on Power BI web: https://app.powerbi.com/view?r=eyJrIjoiNzZkZGEyZmUtNWQ4YS00NjQwLTgwYzktZWQ4ZTFhY2Q2OGYyIiwidCI6ImY1YTgxMzY2LWVjOWQtNDdhZC05YThmLWI0MWFkZjRlOTRmOCIsImMiOjl9&pageName=ReportSection
