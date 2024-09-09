# CREATE ALTER TABLE:

```
create database `db_loja`;

use `db_loja`;

create table cliente (
	numero int,
    nome int,
    cpf int,
    profissao float
);

create table pedido (
	idpedido int,
    cliente varchar(45),
    produto int,
    funcionario varchar(45)
);

create table produto (
	codigo int,
    desconto varchar(45),
    valor varchar(45)
);

create table funcionario (
	cod int,
    nome int,
    cpf varchar(45)
);
alter table cliente rename `tb_cliente`;
    
alter table `tb_cliente` change column numero `cliente_cod` int primary key not null auto_increment;
    
alter table `tb_cliente` change column nome `cli_nome` varchar(45);
    
alter table `tb_cliente` change column cpf `cli_cpf` varchar(14);
    
alter table `tb_cliente` change column profissao `cli_profissao` varchar(45);
    
alter table pedido rename `tb_pedido`;
    
alter table `tb_pedido` change column idpedido `pedido_cod` int primary key not null auto_increment;
    
alter table `tb_pedido` change column cliente `ped_cliente_cod` int;
    
alter table `tb_pedido` add foreign key (`ped_cliente_cod`) references `tb_cliente` (`cliente_cod`);
    
alter table `tb_pedido` change column produto `ped_produto_cod` int;
    
alter table `tb_pedido` change column funcionario `ped_funcionario_cod` int;
    
alter table produto rename `tb_produto`;
    
alter table `tb_produto` change column codigo `produto_cod` int primary key not null auto_increment;
    
alter table `tb_produto` change column desconto `prod_desconto` float;

alter table `tb_produto` modify column `prod_desconto` varchar(4);

alter table `tb_produto` change column valor `prod_valor` float;
    
alter table funcionario rename `tb_funcionario`;
    
alter table `tb_funcionario` change column cod `funcionario_cod` int primary key not null auto_increment;
    
alter table `tb_funcionario` change column nome `fun_nome` varchar(45);
    
alter table `tb_funcionario` change column cpf `fun_cpf` varchar(14);

alter table `tb_pedido` add foreign key (`ped_produto_cod`) references `tb_produto` (`produto_cod`); /*Tentar essa de novo depois!*/
    
alter table `tb_pedido` add foreign key (`ped_funcionario_cod`) references `tb_funcionario` (`funcionario_cod`); /*Tentar essa de novo depois!*/
```
