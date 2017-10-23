# userLogoutAfter10Sec
user will logout automatically after 10secs ,if he has no response

							<script type="text/javascript">
						
								Script for logout session
								var _imin, _isec, _MIN = 0, IDLE_TIME = 0;

								//_imin = 0; // IDLE time in minutes
								_isec = 11;

								// On Mouse Move
								document.addEventListener('mousemove', function(){
									//  _MIN = 0;
									IDLE_TIME = 0;
								});

								// On Click
								document.addEventListener('click', function(){
									//_MIN = 0;
									IDLE_TIME = 0;
								});

								// On Key Press
								document.addEventListener('keypress', function(){
									//_MIN = 0;
									IDLE_TIME = 0;
								});

								window.setInterval('getIdleTime()', 1000);

								function getIdleTime(){
									var _minute, _sec, _nmin, _nsec;

									IDLE_TIME++;

									if( (_isec - IDLE_TIME) === 0 ){
										//_MIN++;
										alert('Your Session has expired!!!!');
										document.location.href = '?action=logout';
										IDLE_TIME = 0;
									}
									_sec    = _isec - IDLE_TIME;

									//_nmin = (_minute.toString().length == 1) ? '0' + _minute : _minute;
									_nsec = (_sec.toString().length === 1) ? '0' + _sec : _sec;

									document.getElementById('SetIdleTime').innerHTML =  _nsec + " seconds";
								}
                                 <li class="active"><span id="SetIdleTime"></span></li>
								
							</script>

