<template>
<v-app>
    <v-app-bar app color="primary" dark>

        <v-app-bar-nav-icon @click="drawer=true"></v-app-bar-nav-icon>
        <v-toolbar-title></v-toolbar-title>
        <v-spacer></v-spacer>

        <!-- 
            <v-btn text rounded>Home</v-btn>
            <v-btn text rounded>Login</v-btn>
            <v-btn text rounded>About</v-btn>
            <v-btn text rounded>Contact us</v-btn>-->
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>

        <v-list-item>
            <v-layout wrap>
                <v-flex sm12 mx-auto>
                    <v-list-item-avatar>
                        <v-img src="@/assets/logo_con.png"></v-img>
                    </v-list-item-avatar>
                </v-flex>
                <v-flex sm12>
                    <v-list-item-content>
                        <v-list-item-title>Conagopare Chimborazo</v-list-item-title>
                    </v-list-item-content>
                </v-flex>
            </v-layout>

        </v-list-item>
        <!-- /////////////////////////////////////////////////////////// -->
        <v-divider></v-divider>
        <v-card class="    gradienteapp mb-2 mt-2">
            <v-list-item v-for="item in inicio" :key="item.title" :to="item.link" link color="white">

                <v-list-item-icon color="white">
                    <v-icon color="primary" class="white--text">{{item.icon}} </v-icon>
                </v-list-item-icon>
                <v-list-item-title class="primary--text">{{item.title}} </v-list-item-title>

            </v-list-item>
        </v-card>
        <v-card class="mb-2">
            <v-list-group :value="false" prepend-icon="church">
                <!--  -->
                <template v-slot:activator>
                    <v-list-item-title>Cementerio</v-list-item-title>
                </template>

                <!-- <v-list-group no-action sub-group>
                <template v-slot:activator>
                    <v-list-item-content>
                        <v-list-item-title>Cementerio</v-list-item-title>
                    </v-list-item-content>
                </template>

                <v-list-item v-for="cementerio in cementerios" :key="cementerio.title" :to="cementerio.link" link>

                    <v-list-item-icon>
                        <v-icon v-text="icon">{{cementerio.icon}} </v-icon>
                    </v-list-item-icon>
                    <v-list-item-title>{{cementerio.title}} </v-list-item-title>
                </v-list-item>
            </v-list-group>-->

                <v-list-group no-action sub-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title>Bloques</v-list-item-title>
                        </v-list-item-content>

                    </template>

                    <v-list-item v-for="bloque in bloques" :key="bloque.title" :to="bloque.link" link>

                        <v-list-item-icon>
                            <v-icon v-text="icon">{{bloque.icon}} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{bloque.title}} </v-list-item-title>
                    </v-list-item>
                </v-list-group>

                <v-list-group no-action sub-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title>Nichos</v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="nicho in nichos" :key="nicho.title" :to="nicho.link" link>

                        <v-list-item-icon>
                            <v-icon v-text="icon">{{nicho.icon}} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{nicho.title}} </v-list-item-title>
                    </v-list-item>
                </v-list-group>

            </v-list-group>
        </v-card>
        <v-card class="mb-2" >

            <v-list-group :value="false" prepend-icon="checklist">
                <template v-slot:activator>
                    <v-list-item-title>Asignación</v-list-item-title>
                </template>
                <v-list-group no-action sub-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title>Representante</v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="representacion in representaciones" :key="representacion.title" :to="representacion.link" link>

                        <v-list-item-icon>
                            <v-icon v-text="icon">{{representacion.icon}} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{representacion.title}} </v-list-item-title>
                    </v-list-item>
                </v-list-group>
                <v-list-group no-action sub-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title>Fallecidos</v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="asignacion in asignaciones" :key="asignacion.title" :to="asignacion.link" link>

                        <v-list-item-icon>
                            <v-icon v-text="icon">{{asignacion.icon}} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{asignacion.title}} </v-list-item-title>
                    </v-list-item>
                </v-list-group>
                <!--<v-list-group no-action sub-group>
                <template v-slot:activator>
                    <v-list-item-content>
                        <v-list-item-title>Listar</v-list-item-title>
                    </v-list-item-content>
                </template>

                <v-list-item v-for="lista in listas" :key="lista.title" :to="lista.link" link>

                    <v-list-item-icon>
                        <v-icon v-text="icon">{{lista.icon}} </v-icon>
                    </v-list-item-icon>
                    <v-list-item-title>{{lista.title}} </v-list-item-title>
                </v-list-item>
            </v-list-group>-->

            </v-list-group>
        </v-card>
    
        <v-card class="mb-2">

            <v-list-group :value="false" prepend-icon="attach_money">
                <template v-slot:activator>
                    <v-list-item-title>Recaudación</v-list-item-title>
                </template>
                <v-list-group no-action sub-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title>Pago</v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="pago in pagos" :key="pago.title" :to="pago.link" link>

                        <v-list-item-icon>
                            <v-icon v-text="icon">{{pago.icon}} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{pago.title}} </v-list-item-title>
                    </v-list-item>
                </v-list-group>
                <v-list-group no-action sub-group>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title>Reportes</v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="reportepago in reportepagos" :key="reportepago.title" :to="reportepago.link" link>

                        <v-list-item-icon>
                            <v-icon v-text="icon">{{reportepago.icon}} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{reportepago.title}} </v-list-item-title>
                    </v-list-item>
                </v-list-group>

            </v-list-group>
        </v-card>
        <!--  <v-list-group :value="false" prepend-icon="settings">
            <template v-slot:activator>
                <v-list-item-title>Configuraciones</v-list-item-title>
            </template>
            <v-list-group no-action sub-group>
                <template v-slot:activator>
                    <v-list-item-content>
                        <v-list-item-title>Usuarios Sistema</v-list-item-title>
                    </v-list-item-content>
                </template>

                <v-list-item v-for="configuracion in configuraciones" :key="configuracion.title" :to="configuracion.link" link>

                    <v-list-item-icon>
                        <v-icon v-text="icon">{{configuracion.icon}} </v-icon>
                    </v-list-item-icon>
                    <v-list-item-title>{{configuracion.title}} </v-list-item-title>
                </v-list-item>
            </v-list-group>

        </v-list-group>-->

    </v-navigation-drawer>

    <v-main>
        <router-view />
    </v-main>
</v-app>
</template>

<script>
export default {
    name: 'App',

    data() {
        return {
            drawer: false,
            icon: '',
            inicio: [{
                icon: 'home',
                title: 'Inicio',
                link: '/'
            }, ],
            cementerios: [{
                    icon: 'home_work',
                    title: 'Nuevo',
                    link: '/cementerio'
                },
                {
                    icon: 'list',
                    title: 'Listar',
                    link: '/listarcementerio'
                },

            ],
            //
            bloques: [{
                    icon: 'grid_view ',
                    title: 'Nuevo',
                    link: '/bloque'
                },
                {
                    icon: 'list',
                    title: 'Listar',
                    link: '/listarbloque'
                },

            ],
            //
            nichos: [{
                    icon: 'mdi-grave-stone ',
                    title: 'Nuevo',
                    link: '/nicho'
                },
                {
                    icon: 'list',
                    title: 'Listar',
                    link: '/listarnicho'
                },
                {
                    icon: 'mdi-state-machine',
                    title: 'Tipo',
                    link: '/tiponicho'
                },
                /* {
                      icon: 'mdi-chemical-weapon ',
                      title: 'Estado',
                      link: '/estadonicho'
                  },*/
                {
                    icon: 'mdi-format-list-bulleted-square',
                    title: 'Tipo/Estado',
                    link: '/listartipoyestadonicho'
                },
            ],
            //
            asignaciones: [{
                    icon: 'supervisor_account',
                    title: 'Asignar',
                    link: '/asignar'
                },
                {
                    icon: 'view_list',
                    title: 'Listar',
                    link: '/listarfallecimientos'
                },

            ],
            //
            /* listas: [

             ],*/
            //
            representaciones: [{
                    icon: 'mdi-account-tie',
                    title: 'Nuevo',
                    link: '/representante'
                },
                /*{
                    icon: 'summarize',
                    title: 'Listar',
                    link: '/reportereprefalle'
                },*/
                {
                    icon: 'list_alt',
                    title: 'Listar',
                    link: '/listarepresentantes'
                },

            ],
            //
            pagos: [{
                    icon: 'payments',
                    title: 'Pago',
                    link: '/pago'
                },
              /*  {
                    icon: 'price_change',
                    title: 'Estado',
                    link: '/estadopago'
                },
                {
                    icon: 'hourglass_bottom',
                    title: 'Periodo',
                    link: '/periodopago'
                },*/

            ],
            // 
            reportepagos: [{
                    icon: 'summarize',
                    title: 'Pagos',
                    link: '/reportepagos'
                },
             /*   {
                    icon: 'sync',
                    title: 'Actualizar',
                    link: '/reporte'
                },*/

            ],
            // 
            /*  configuraciones: [{
                      icon: 'person_add_alt',
                      title: 'Nuevo',
                      link: '/registro'
                  },
                  {
                      icon: 'mdi-account-details-outline ',
                      title: 'Tipo',
                      link: '/tipousuario'
                  },
                  {
                      icon: 'list',
                      title: 'Listar',
                      link: '/listarusuarios'
                  },

              ],*/
            //
        }
    }

};
</script>
