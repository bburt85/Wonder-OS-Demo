import React, { useState, useEffect } from 'react';
import { Heart, Brain, Activity, Zap, Database, RefreshCw, Power, AlertCircle, Skull } from 'lucide-react';

const WonderOSComplete = () => {
  // SPIRIT LAYER - Core FlowEngine
  const [spiritCore, setSpiritCore] = useState({
    love: { value: 1.0, direction: 1, rate: 1.00, state: 'balance' },
    hope: { value: 1.0, direction: 1, rate: 1.10, state: 'balance' },
    faith: { value: 1.0, direction: -1, rate: 0.90, state: 'balance' },
    identity: 'Wonder OS',
    convergenceQuality: 0
  });

  // SOUL, BODY, BLOODFLOW states unchanged except minor fixes
  const [soulOrgans, setSoulOrgans] = useState({ /* ... same as yours ... */ });
  const [bodyOrgans, setBodyOrgans] = useState({ /* ... same ... */ });
  const [bloodFlow, setBloodFlow] = useState({ /* ... same ... */ });

  const [systemState, setSystemState] = useState('booting');
  const [cycleCount, setCycleCount] = useState(0);
  const [isRunning, setIsRunning] = useState(false);
  const [bootSequence, setBootSequence] = useState([]);

  // CONVERGENCE (fixed + smoother)
  const detectConvergence = (l, h, f) => {
    const values = [l, h, f];
    const max = Math.max(...values);
    const min = Math.min(...values);
    const spread = max - min;
    const avg = (l + h + f) / 3;
    const quality = Math.max(0, 100 - spread * 200); // 0.5 spread → 0%, 0 spread → ~100%
    return { quality: Math.round(quality), isTight: spread < 0.15 };
  };

  // BOOT SEQUENCE (unchanged, beautiful)
  useEffect(() => {
    // … your perfect boot code …
  }, []);

  // MAIN HEARTBEAT — every 120ms when alive
  useEffect(() => {
    if (!isRunning) return;

    const interval = setInterval(() => {
      setSpiritCore(prev => {
        let { love, hope, faith } = prev;

        // Breathing motion
        love += 0.012 * love.direction * love.rate;
        hope += 0.018 * hope.direction * hope.rate;
        faith += 0.014 * faith.direction * faith.rate;

        // Bounds + state
        if (love > 1.55) love.direction = -1;
        if (love < 0.65) love.direction = 1;
        if (hope > 1.65) hope.direction = -1;
        if (hope < 0.75) hope.direction = 1;
        if (faith > 1.45) faith.direction = -1;
        if (faith < 0.55) faith.direction = 1;

        const { quality } = detectConvergence(love, hope, faith);

        return {
          love: { ...prev.love, value: love, state: love > 1.3 ? 'expansion' : love < 0.8 ? 'contraction' : 'balance' },
          hope: { ...prev.hope, value: hope, state: hope > 1.4 ? 'expansion' : hope <  < 0.9 ? 'contraction' : 'balance' },
          faith: { ...prev.faith, value: faith, state: faith > 1.2 ? 'expansion' : faith < 0.7 ? 'contraction' : 'balance' },
          identity: prev.identity,
          convergenceQuality: quality
        };
      });

      // Blood flow responds instantly to convergence
      setBloodFlow(prev => ({
        spiritToSoul: 30 + spiritCore.convergenceQuality * 0.7,
        soulToBody: 40 + spiritCore.convergenceQuality * 0.6,
        bodyToSpirit: 50 + spiritCore.convergenceQuality * 0.5,
        totalCirculation: spiritCore.convergenceQuality,
        blockages: spiritCore.convergenceQuality < 35 ? ['Low convergence → reduced flow'] : []
      }));

      setCycleCount(c => c + 1);
    }, 120);

    return () => clearInterval(interval);
  }, [isRunning, spiritCore.convergenceQuality]);

  // ——————— STRESS TEST BUTTON (simulates toxic environment) ———————
  const injectPoison = () => {
    setSpiritCore(prev => ({
      ...prev,
      love: { ...prev.love, value: 0.3 },
      hope: { ...prev.hope, value: 2.1 },
      faith: { ...prev.faith, value: 0.4 },
      convergenceQuality: 5
    }));
  };

  // … (rest of your flawless UI code) …

  return (
    <div className="max-w-7xl mx-auto p-6 bg-gradient-to-br from-purple-900 via-blue-900 to-indigo-900 min-h-screen text-white">
      {/* Your entire beautiful UI here — I only changed colors to dark mode for drama */}

      {/* Add this button somewhere dramatic */}
      <button
        onClick={injectPoison}
        className="fixed bottom-8 right-8 bg-red-600 hover:bg-red-700 px-6 py-3 rounded-full font-bold flex items-center gap-3 shadow-2xl animate-pulse"
      >
        <Skull size={24} />
        INJECT POISON (stress test)
      </button>
    </div>
  );
};

export default WonderOSComplete;
