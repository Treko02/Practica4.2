#include <iostream>
#define CATCH_CONFIG_MAIN
#include "catch.hpp"

using namespace std;


void busqSecR(int v[], int n, int clave, bool & esta, int &pos)
{
    if (n==0){
        if (clave!=v[0]){
            esta= false;
            pos=-1;
        }else{
            esta=true;
            pos=0;
        }
    }else{
        if (clave==v[n]){
            esta= true;
            pos=n;
        }else{
            busqSecR(v, n-1, clave, & esta, & pos);
        }
    }
}

void busqDicRInm (int v[], int iz, int der, int clave, bool &esta, int &pos)
{

}

void busqDicR (int v[], int n, int clave, bool &esta, int &pos)
{

}

//Subalgoritmo para comprobar automÃ¡ticamente si el resultado de buscar es correcto
bool comprobarBusqueda(int v[], int n, int clave, bool esta, int pos)
{
    if (pos==-1) //Si devolvemos -1 es que no estaba
        {
        if (esta) return false; //Si pos es -1, entonces esta deberÃ­a ser falso. Si es true, entonces la funcion estaba mal implementada.
        for (int i = 0; i<n; i++)
            if (v[i]==clave)
                return false; //Significa que lo ha encontrado y que entonces nuestra funciÃ³n falla
                return true; //Si llegamos aquÃ­ es que todo ha ido bien (la clave no estaba en el vector).
        }
    else return (v[pos]==clave && esta); //Comprobamos que realmente estaba.

}

TEST_CASE( "Comprobando busqueda secuencial", "[busqSecR]" ) {
    int v[] = {2,5,8,9,10,11,18,19,25,26,29,35,44,59,64,69,73};
    int n=sizeof(v)/sizeof(*v);
    bool esta=false;
    int pos = 8;
    busqSecR(v,n,11,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,11,esta,pos));
    busqSecR(v,n,2,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,2,esta,pos));
    busqSecR(v,n,80,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,80,esta,pos));
    busqSecR(v,n,36,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,36,esta,pos));
}


TEST_CASE( "Comprobando busqueda dicotomica", "[busqDicR]" ) {

    int v[] = {2,5,8,9,10,11,18,19,25,26,29,35,44,59,64,69,73};
    int n=sizeof(v)/sizeof(*v);
    bool esta=false;
    int pos = 8;
    busqDicR(v,n,11,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,11,esta,pos));
    busqDicR(v,n,2,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,2,esta,pos));
    busqDicR(v,n,80,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,80,esta,pos));
    busqDicR(v,n,36,esta,pos);
    REQUIRE(comprobarBusqueda(v,n,36,esta,pos));
}


